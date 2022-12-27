## Lancache images for ARMv7 and ARM64
![Docker Pulls](https://img.shields.io/docker/pulls/joshuasing/lancache-monolithic?label=Monolithic) ![Docker Pulls](https://img.shields.io/docker/pulls/joshuasing/lancache-dns?label=Lancache-dns) ![Docker Pulls](https://img.shields.io/docker/pulls/joshuasing/lancache-sniproxy?label=Sniproxy) ![Docker Pulls](https://img.shields.io/docker/pulls/joshuasing/lancache-generic?label=Generic)

This is an unofficial set of images for running Lancache in Docker on ARMv7 and ARM64.  
This is primarily based on [jrcichra/lancache-rpi](https://github.com/jrcichra/lancache-rpi), with some improvements, and I plan to maintain it for the foreseeable future.

### **Warning**
 - NTFS/FAT32 external drives will not work. `nginx` tries to `chown`, which doesn't play nice with Microsoft filesystems. Please use a nix filesystem such as `ext4`.
 - You may experience slower than expected cache speeds if using a Raspberry PI.

### Installation
**Prerequisites**:
 - Docker
 - docker-compose

**Install**
 - `git clone https://github.com/joshuasing/lancache-rpi.git`
 - `cd lancache-rpi`
 - `vi .env` - Make all required configuration changes, and change `LANCACHE_IP` and `DNS_BIND_IP` to the address of the interface you wish to expose Lancache on. `0.0.0.0` will work for all interfaces, however using a single interface is recommended.
 - `docker-compose up -d`
 - Configure the machines you wish to use lancache-dns
 - Further documentation can be found at [lancache.net](https://lancache.net/)

### Testing
http://diagnostics.lancache.net/

### Updates
The Docker images are currently updated weekly, however they may also be updated manually at times.    
Please contact me, either on [Discord](https://discord.hypera.dev/) or using GitHub issues if you need this to be updated, and it hasn't already.  
You can see a full list of Docker images on [Docker Hub](https://hub.docker.com/u/joshuasing).
