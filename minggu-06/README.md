# Redis

### Step 1 - Running A Container
```
$ docker search redis
NAME                             DESCRIPTION                                     STARS               OFFICIAL            AUTOMATED
redis                            Redis is an open source key-value store that…   7412                [OK]
bitnami/redis                    Bitnami Redis Docker Image                      129                                     [OK]
sameersbn/redis                                                                  77                                      [OK]
grokzen/redis-cluster            Redis cluster 3.0, 3.2, 4.0 & 5.0               61
rediscommander/redis-commander   Alpine image for redis-commander - Redis man…   31                                      [OK]
kubeguide/redis-master           redis-master with "Hello World!"                30
redislabs/redis                  Clustered in-memory database engine compatib…   23
oliver006/redis_exporter          Prometheus Exporter for Redis Metrics. Supp…   18
arm32v7/redis                    Redis is an open source key-value store that…   17
redislabs/redisearch             Redis With the RedisSearch module pre-loaded…   17
webhippie/redis                  Docker images for Redis                         10                                      [OK]
s7anley/redis-sentinel-docker    Redis Sentinel                                  9                                      [OK]
bitnami/redis-sentinel           Bitnami Docker Image for Redis Sentinel         8                                      [OK]
insready/redis-stat              Docker image for the real-time Redis monitor…   8                                      [OK]
redislabs/redisgraph             A graph database module for Redis               8                                      [OK]
arm64v8/redis                    Redis is an open source key-value store that…   6
centos/redis-32-centos7          Redis in-memory data structure store, used a…   4
redislabs/redismod               An automated build of redismod - latest Redi…   4                                      [OK]
circleci/redis                   CircleCI images for Redis                       2                                      [OK]
frodenas/redis                   A Docker Image for Redis                        2                                      [OK]
tiredofit/redis                  Redis Server w/ Zabbix monitoring and S6 Ove…   1                                      [OK]
runnable/redis-stunnel           stunnel to redis provided by linking contain…   1                                      [OK]
wodby/redis                      Redis container image with orchestration        1                                      [OK]
xetamus/redis-resource           forked redis-resource                           0                                      [OK]
cflondonservices/redis           Docker image for running redis                  0
```
Menjalankan Redis
```
$ docker run -d redis
2da8911f436b826e8205654dbe4530c5544ed6aaf1c0c1877a6620c4afcc40cb
```

### Step 2 - Finding Running Containers
Melihat Container yang _running_
```
$ docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED  STATUS              PORTS               NAMES
2da8911f436b        redis               "docker-entrypoint.s…"   49 seconds ago  Up 47 seconds       6379/tcp            vibrant_cray
```
Melihat detail Container
```
$ docker inspect 2da8911f436b
[
    {
        "Id": "2da8911f436b826e8205654dbe4530c5544ed6aaf1c0c1877a6620c4afcc40cb",
        "Created": "2019-10-15T13:30:36.884862861Z",
        "Path": "docker-entrypoint.sh",
        "Args": [
            "redis-server"
        ],
        "State": {
            "Status": "running",
            "Running": true,
            "Paused": false,
            "Restarting": false,
            "OOMKilled": false,
            "Dead": false,
            "Pid": 741,
            "ExitCode": 0,
            "Error": "",
            "StartedAt": "2019-10-15T13:30:37.410964715Z",
            "FinishedAt": "0001-01-01T00:00:00Z"
        },
        "Image": "sha256:4760dc956b2ddc9ac1c508936e39b63a22c6f0640ef58c1b10ff73f04e253ffe",
        "ResolvConfPath": "/var/lib/docker/containers/2da8911f436b826e8205654dbe4530c5544ed6aaf1c0c1877a6620c4afcc40cb/resolv.conf",
        "HostnamePath": "/var/lib/docker/containers/2da8911f436b826e8205654dbe4530c5544ed6aaf1c0c1877a6620c4afcc40cb/hostname",
        "HostsPath": "/var/lib/docker/containers/2da8911f436b826e8205654dbe4530c5544ed6aaf1c0c1877a6620c4afcc40cb/hosts",
        "LogPath": "/var/lib/docker/containers/2da8911f436b826e8205654dbe4530c5544ed6aaf1c0c1877a6620c4afcc40cb/2da8911f436b826e8205654dbe4530c5544ed6aaf1c0c1877a6620c4afcc40cb-json.log",
        "Name": "/vibrant_cray",
        "RestartCount": 0,
        "Driver": "overlay",
        "Platform": "linux",
        "MountLabel": "",
        "ProcessLabel": "",
        "AppArmorProfile": "",
        "ExecIDs": null,
        "HostConfig": {
            "Binds": null,
            "ContainerIDFile": "",
            "LogConfig": {
                "Type": "json-file",
                "Config": {}
            },
            "NetworkMode": "default",
            "PortBindings": {},
            "RestartPolicy": {
                "Name": "no",
                "MaximumRetryCount": 0
            },
            "AutoRemove": false,
            "VolumeDriver": "",
            "VolumesFrom": null,
            "CapAdd": null,
            "CapDrop": null,
            "Dns": [],
            "DnsOptions": [],
            "DnsSearch": [],
            "ExtraHosts": null,
            "GroupAdd": null,
            "IpcMode": "shareable",
            "Cgroup": "",
            "Links": null,
            "OomScoreAdj": 0,
            "PidMode": "",
            "Privileged": false,
            "PublishAllPorts": false,
            "ReadonlyRootfs": false,
            "SecurityOpt": null,
            "UTSMode": "",
            "UsernsMode": "",
            "ShmSize": 67108864,
            "Runtime": "runc",
            "ConsoleSize": [
                0,
                0
            ],
            "Isolation": "",
            "CpuShares": 0,
            "Memory": 0,
            "NanoCpus": 0,
            "CgroupParent": "",
            "BlkioWeight": 0,
            "BlkioWeightDevice": [],
            "BlkioDeviceReadBps": null,
            "BlkioDeviceWriteBps": null,
            "BlkioDeviceReadIOps": null,
            "BlkioDeviceWriteIOps": null,
            "CpuPeriod": 0,
            "CpuQuota": 0,
            "CpuRealtimePeriod": 0,
            "CpuRealtimeRuntime": 0,
            "CpusetCpus": "",
            "CpusetMems": "",
            "Devices": [],
            "DeviceCgroupRules": null,
            "DiskQuota": 0,
            "KernelMemory": 0,
            "MemoryReservation": 0,
            "MemorySwap": 0,
            "MemorySwappiness": null,
            "OomKillDisable": false,
            "PidsLimit": 0,
            "Ulimits": null,
            "CpuCount": 0,
            "CpuPercent": 0,
            "IOMaximumIOps": 0,
            "IOMaximumBandwidth": 0
        },
        "GraphDriver": {
            "Data": {
                "LowerDir": "/var/lib/docker/overlay/d5d206b9df9a3642afb5a4767df56cf1770db74b9de93724098e86acf3ff97f3/root",
                "MergedDir": "/var/lib/docker/overlay/5b13ea454798eb5caf6fb06774ce761c82cfd9925f286575af6fed94237c3ba3/merged",
                "UpperDir": "/var/lib/docker/overlay/5b13ea454798eb5caf6fb06774ce761c82cfd9925f286575af6fed94237c3ba3/upper",
                "WorkDir": "/var/lib/docker/overlay/5b13ea454798eb5caf6fb06774ce761c82cfd9925f286575af6fed94237c3ba3/work"
            },
            "Name": "overlay"
        },
        "Mounts": [
            {
                "Type": "volume",
                "Name": "74735c95d1aca85a72278460fcb452e4fca37a8d8d3c3a3601a8283863886e1c",
                "Source": "/var/lib/docker/volumes/74735c95d1aca85a72278460fcb452e4fca37a8d8d3c3a3601a8283863886e1c/_data",
                "Destination": "/data",
                "Driver": "local",
                "Mode": "",
                "RW": true,
                "Propagation": ""
            }
        ],
        "Config": {
            "Hostname": "2da8911f436b",
            "Domainname": "",
            "User": "",
            "AttachStdin": false,
            "AttachStdout": false,
            "AttachStderr": false,
            "ExposedPorts": {
                "6379/tcp": {}
            },
            "Tty": false,
            "OpenStdin": false,
            "StdinOnce": false,
            "Env": [
                "PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin",
                "GOSU_VERSION=1.10",
                "REDIS_VERSION=4.0.8",
                "REDIS_DOWNLOAD_URL=http://download.redis.io/releases/redis-4.0.8.tar.gz",
                "REDIS_DOWNLOAD_SHA=ff0c38b8c156319249fec61e5018cf5b5fe63a65b61690bec798f4c998c232ad"
            ],
            "Cmd": [
                "redis-server"
            ],
            "ArgsEscaped": true,
            "Image": "redis",
            "Volumes": {
                "/data": {}
            },
            "WorkingDir": "/data",
            "Entrypoint": [
                "docker-entrypoint.sh"
            ],
            "OnBuild": null,
            "Labels": {}
        },
        "NetworkSettings": {
            "Bridge": "",
            "SandboxID": "7df3be78af8491887ca92c66533de800ad2bf2a4a042b676638f47e63caab228",
            "HairpinMode": false,
            "LinkLocalIPv6Address": "",
            "LinkLocalIPv6PrefixLen": 0,
            "Ports": {
                "6379/tcp": null
            },
            "SandboxKey": "/var/run/docker/netns/7df3be78af84",
            "SecondaryIPAddresses": null,
            "SecondaryIPv6Addresses": null,
            "EndpointID": "96844252ef18f944548b3f90d48db032300133e35fb9473c69dc7f3644c06915",
            "Gateway": "172.18.0.1",
            "GlobalIPv6Address": "",
            "GlobalIPv6PrefixLen": 0,
            "IPAddress": "172.18.0.2",
            "IPPrefixLen": 24,
            "IPv6Gateway": "",
            "MacAddress": "02:42:ac:12:00:02",
            "Networks": {
                "bridge": {
                    "IPAMConfig": null,
                    "Links": null,
                    "Aliases": null,
                    "NetworkID": "6026e4d8591ea8ad6784db698531593b006c9f20935dbf2dd3348db23fc79063",
                    "EndpointID": "96844252ef18f944548b3f90d48db032300133e35fb9473c69dc7f3644c06915",
                    "Gateway": "172.18.0.1",
                    "IPAddress": "172.18.0.2",
                    "IPPrefixLen": 24,
                    "IPv6Gateway": "",
                    "GlobalIPv6Address": "",
                    "GlobalIPv6PrefixLen": 0,
                    "MacAddress": "02:42:ac:12:00:02",
                    "DriverOpts": null
                }
            }
        }
    }
]
```
Melihat log container
```
$ docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED  STATUS              PORTS               NAMES
2da8911f436b        redis               "docker-entrypoint.s…"   3 minutes ago  Up 3 minutes        6379/tcp            vibrant_cray
$ docker logs 2da8911f436b
1:C 15 Oct 13:30:37.453 # oO0OoO0OoO0Oo Redis is starting oO0OoO0OoO0Oo
1:C 15 Oct 13:30:37.454 # Redis version=4.0.8, bits=64, commit=00000000, modified=0, pid=1, just started
1:C 15 Oct 13:30:37.454 # Warning: no config file specified, using the default config. In order to specify a config file use redis-server /path/to/redis.conf
1:M 15 Oct 13:30:37.456 * Running mode=standalone, port=6379.
1:M 15 Oct 13:30:37.456 # WARNING: The TCP backlog setting of 511 cannot be enforced because /proc/sys/net/core/somaxconn is set to the lower value of 128.
1:M 15 Oct 13:30:37.456 # Server initialized
1:M 15 Oct 13:30:37.457 # WARNING overcommit_memory is set to 0! Background save may fail under low memory condition. To fix this issue add 'vm.overcommit_memory = 1' to /etc/sysctl.conf and then reboot or run the command 'sysctl vm.overcommit_memory=1' for this to take effect.
1:M 15 Oct 13:30:37.457 # WARNING you have Transparent Huge Pages (THP) support enabled in your kernel. This will create latency and memory usage issues with Redis. To fix this issue run the command 'echo never > /sys/kernel/mm/transparent_hugepage/enabled' as root, and add it to your /etc/rc.local in order to retain the setting after a reboot. Redis must be restarted after THP is disabled.
1:M 15 Oct 13:30:37.457 * Ready to accept connections
```
### Step 3 - Accessing Redis
```
$ docker run -d --name redisHostPort -p 6379:6379 redis:latest
ab6c0b5c81de5297c44cef1817a2a3bc7a138ad118a8d9d9b5204ab2fd315eaa

$ docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED  STATUS              PORTS                    NAMES
ab6c0b5c81de        redis:latest        "docker-entrypoint.s…"   15 seconds ago  Up 7 seconds        0.0.0.0:6379->6379/tcp   redisHostPort
2da8911f436b        redis               "docker-entrypoint.s…"   5 minutes ago  Up 5 minutes        6379/tcp                 vibrant_cray
```
### Step 4 - Accessing Redis
```
$ docker run -d --name redisDynamic -p 6379 redis:latest
8e8549c346bb9c11ba62cde82c795cd79c849179f49180a4e3e88c458d15e2e7

$ docker port redisDynamic 6379
0.0.0.0:32768

$ docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED  STATUS              PORTS                     NAMES
8e8549c346bb        redis:latest        "docker-entrypoint.s…"   22 seconds ago  Up 10 seconds       0.0.0.0:32768->6379/tcp   redisDynamic
ab6c0b5c81de        redis:latest        "docker-entrypoint.s…"   2 minutes ago  Up 2 minutes        0.0.0.0:6379->6379/tcp    redisHostPort
2da8911f436b        redis               "docker-entrypoint.s…"   7 minutes ago  Up 7 minutes        6379/tcp                  vibrant_cray
```

### Step 5 - Persisting Data
```
$ docker run -d --name redisMapped -v /opt/docker/data/redis:/data redis
2c59c3d1f1dd4a2a32533ad6c7013e3a91639e8c3c5f8b7495538a321dca5227

$ docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED   STATUS              PORTS                     NAMES
2c59c3d1f1dd        redis               "docker-entrypoint.s…"   About a minute ago   Up About a minute   6379/tcp                  redisMapped
8e8549c346bb        redis:latest        "docker-entrypoint.s…"   2 minutes ago   Up 2 minutes        0.0.0.0:32768->6379/tcp   redisDynamic
ab6c0b5c81de        redis:latest        "docker-entrypoint.s…"   4 minutes ago   Up 3 minutes        0.0.0.0:6379->6379/tcp    redisHostPort
2da8911f436b        redis               "docker-entrypoint.s…"   8 minutes ago   Up 8 minutes        6379/tcp                  vibrant_cray
```

### Step 6 - Running A Container In The Foreground
```
$ docker run -it ubuntu bash
root@1d43890681ca:/#
```

# Nginx
#### Step 1 - Create Dockerfile
Membuat Dockerfile
```
FROM nginx:alpine
COPY . /usr/share/nginx/html
```

#### Step 2 - Build Docker Image
Melalui terminal jalankan perintah berikut
```
$ docker build -t webserver-image:v1 .

Sending build context to Docker daemon  3.072kB
Step 1/2 : FROM nginx:alpine
 ---> 4d3c246dfef2
Step 2/2 : COPY . /usr/share/nginx/html
 ---> 0e6105acc7ef
Successfully built 0e6105acc7ef
Successfully tagged webserver-image:v1
```
#### Step 3 - Run
Menjalankan nginx
```
$ docker run -d -p 80:80 webserver-image:v1
2e73d86313b0cdb71a865cac4bede5e27c47c93fd4beb0a699420c300eb77d19
$ docker ps | grep nginx
2e73d86313b0        webserver-image:v1   "nginx -g 'daemon of…"   19 seconds ago   Up 12 seconds       0.0.0.0:80->80/tcp   elegant_vaughan
```
mencoba mengakses nginx menggunakan curl
```
$ curl docker
<h1>Hello World</h1>
```