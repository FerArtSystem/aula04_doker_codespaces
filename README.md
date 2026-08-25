# aula04_doker_codespaces
Está é a aula 04, feita no dia 24/08/2026 a qual tratará de Doker e Codespaces
'''
$ docker --version
Docker version 29.3.0-1, build 5927d80c76b3ce5cf782be818922966e8a0d87a3

$ docker info
Client:
 Version:    29.3.0-1
 Context:    default
 Debug Mode: false
 Plugins:
  buildx: Docker Buildx (Docker Inc.)
    Version:  v0.32.1
    Path:     /usr/libexec/docker/cli-plugins/docker-buildx
  compose: Docker Compose (Docker Inc.)
    Version:  v2.40.3
    Path:     /usr/libexec/docker/cli-plugins/docker-compose

Server:
 Containers: 0
  Running: 0
  Paused: 0
  Stopped: 0
 Images: 0
 Server Version: 29.3.0-1
 Storage Driver: overlayfs
  driver-type: io.containerd.snapshotter.v1
 Logging Driver: json-file
 Cgroup Driver: cgroupfs
 Cgroup Version: 2
 Plugins:
  Volume: local
  Network: bridge host ipvlan macvlan null overlay
  Log: awslogs fluentd gcplogs gelf journald json-file local splunk syslog
 CDI spec directories:
  /etc/cdi
  /var/run/cdi
 Swarm: inactive
 Runtimes: io.containerd.runc.v2 runc
 Default Runtime: runc
 Init Binary: docker-init
 containerd version: dea7da592f5d1d2b7755e3a161be07f43fad8f75
 runc version: 8bd78a9977e604c4d5f67a7415d7b8b8c109cdc4
 init version: 
 Security Options:
  apparmor
  seccomp
   Profile: builtin
  cgroupns
 Kernel Version: 6.8.0-1052-azure
 Operating System: Ubuntu 24.04.4 LTS (containerized)
 OSType: linux
 Architecture: x86_64
 CPUs: 2
 Total Memory: 7.758GiB
 Name: codespaces-5de8fa
 ID: 96de4144-6f30-4271-b5a6-aada242f8886
 Docker Root Dir: /var/lib/docker
 Debug Mode: false
 Username: codespacesdev
 Experimental: false
 Insecure Registries:
  ::1/128
  127.0.0.0/8
 Live Restore Enabled: false
 Firewall Backend: iptables
 '''

'''
$ docker pull nginx:latest
latest: Pulling from library/nginx
7eb55399d6de: Pull complete 
f530c3e421fc: Pull complete 
5d480233f531: Pull complete 
746b934a8960: Pull complete 
5508f6432d3e: Pull complete 
128fcc7b23b0: Pull complete 
26c307b5e35a: Pull complete 
3976f7b8a9d7: Download complete 
81dd0279e705: Download complete 
Digest: sha256:0d4374c710a9649200e84f8ef8dbdd4fa76c0c107839cd50f1e42a63916b0f2e
Status: Downloaded newer image for nginx:latest
docker.io/library/nginx:latest


$ docker images                                                                                                      i Info →   U  In Use
IMAGE          ID             DISK USAGE   CONTENT SIZE   EXTRA
nginx:latest   0d4374c710a9        241MB         66.2MB        

$ docker run -d --name meu_nginx -p 8080:80 nginx:latest
e358c24f838dfc7731783be507a97de0801aedc268d90c12cd33bdc5cca3276b

$ docker ps
CONTAINER ID   IMAGE          COMMAND                  CREATED              STATUS              PORTS                                     NAMES
e358c24f838d   nginx:latest   "/docker-entrypoint.…"   About a minute ago   Up About a minute   0.0.0.0:8080->80/tcp, [::]:8080->80/tcp   meu_nginx

$ docker ps --filter name=meu_nginx
CONTAINER ID   IMAGE          COMMAND                  CREATED              STATUS              PORTS                                     NAMES
e358c24f838d   nginx:latest   "/docker-entrypoint.…"   About a minute ago   Up About a minute   0.0.0.0:8080->80/tcp, [::]:8080->80/tcp   meu_nginx

$ docker logs meu_nginx
/docker-entrypoint.sh: /docker-entrypoint.d/ is not empty, will attempt to perform configuration
/docker-entrypoint.sh: Looking for shell scripts in /docker-entrypoint.d/
/docker-entrypoint.sh: Launching /docker-entrypoint.d/10-listen-on-ipv6-by-default.sh
10-listen-on-ipv6-by-default.sh: info: Getting the checksum of /etc/nginx/conf.d/default.conf
10-listen-on-ipv6-by-default.sh: info: Enabled listen on IPv6 in /etc/nginx/conf.d/default.conf
/docker-entrypoint.sh: Sourcing /docker-entrypoint.d/15-local-resolvers.envsh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/20-envsubst-on-templates.sh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/30-tune-worker-processes.sh
/docker-entrypoint.sh: Configuration complete; ready for start up
2026/08/24 23:37:30 [notice] 1#1: using the "epoll" event method
2026/08/24 23:37:30 [notice] 1#1: nginx/1.31.4
2026/08/24 23:37:30 [notice] 1#1: built by gcc 14.2.0 (Debian 14.2.0-19) 
2026/08/24 23:37:30 [notice] 1#1: OS: Linux 6.8.0-1052-azure
2026/08/24 23:37:30 [notice] 1#1: getrlimit(RLIMIT_NOFILE): 1024:524288
2026/08/24 23:37:30 [notice] 1#1: start worker processes
2026/08/24 23:37:30 [notice] 1#1: start worker process 29
2026/08/24 23:37:30 [notice] 1#1: start worker process 30

$ curl -I http://localhost:8080
HTTP/1.1 200 OK
Server: nginx/1.31.4
Date: Mon, 24 Aug 2026 23:40:00 GMT
Content-Type: text/html
Content-Length: 896
Last-Modified: Tue, 11 Aug 2026 20:02:04 GMT
Connection: keep-alive
ETag: "6a7b7fbc-380"
Accept-Ranges: bytes

$ docker exec -it meu_nginx sh
# ls /usr/share/nginx/html
50x.html  index.html
'''

 ![alt text](image.png)

'''
@FerArtSystem ➜ /workspaces/aula04_doker_codespaces (main) $ docker stop meu_nginx
meu_nginx
@FerArtSystem ➜ /workspaces/aula04_doker_codespaces (main) $ docker rm meu_nginx
meu_nginx
@FerArtSystem ➜ /workspaces/aula04_doker_codespaces (main) $ docker ps -a
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
@FerArtSystem ➜ /workspaces/aula04_doker_codespaces (main) $ 
'''
![alt text](image-1.png)
