## 👋 Welcome to alpine 🚀  

alpine README  
  
  
## Install my system scripts  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 sudo systemmgr --config && sudo systemmgr install scripts  
```
  
## Automatic install/update  
  
```shell
dockermgr update os alpine
```
  
## Install and run container
  
```shell
mkdir -p "/var/lib/srv/root/docker/casjaysdev/alpine/latest"
git clone "https://github.com/dockermgr/alpine" "$HOME/.local/share/CasjaysDev/dockermgr/alpine"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/alpine/dockerfs/." "/var/lib/srv/root/docker/casjaysdev/alpine/latest/"
docker run -d \
--restart always \
--privileged \
--name casjaysdev-alpine-latest \
--hostname alpine \
-e TZ=${TIMEZONE:-America/New_York} \
-v "/var/lib/srv/root/docker/casjaysdev/alpine/latest/data:/data:z" \
-v "/var/lib/srv/root/docker/casjaysdev/alpine/latest/config:/config:z" \
casjaysdev/alpine:latest
```
  
## via docker-compose  
  
```yaml
version: "2"
services:
  ProjectName:
    image: casjaysdev/alpine
    container_name: casjaysdev-alpine-latest
    environment:
      - TZ=America/New_York
      - HOSTNAME=alpine
    volumes:
      - "/var/lib/srv/root/docker/casjaysdev/alpine/latest/data:/data:z"
      - "/var/lib/srv/root/docker/casjaysdev/alpine/latest/config:/config:z"
    restart: always
```
  
## Get source files  
  
```shell
dockermgr download src os alpine
```
  
## Build container  
  
```shell
git clone "https://github.com/dockersrc/alpine" "$HOME/Projects/github/dockersrc/alpine"
cd "$HOME/Projects/github/dockersrc/alpine" && buildx all 
```
  
## Authors  
  
🤖 casjay: [Github](https://github.com/casjay) 🤖  
⛵ casjaysdev: [Github](https://github.com/dockersrc) [Docker](https://hub.docker.com/u/casjaysdev) ⛵  
