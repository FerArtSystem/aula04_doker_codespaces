# aula04_doker_codespaces
Está é a aula 04, feita no dia 24/08/2026 a qual tratará de Doker e Codespaces

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
 