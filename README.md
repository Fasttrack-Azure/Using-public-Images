## Using-public-Images

### Pull the public image for Smtp4Dev from Docker Hub
```sh
docker pull rnwood/smtp4dev

Refer: https://hub.docker.com/r/rnwood/smtp4dev
```
### How to run smtp4dev in Docker
Docker images for both Windows and Linux are available. To run with the web interface on port 3000 and SMTP on port 2525:

```
docker run --rm -it -p 3000:80 -p 2525:25 rnwood/smtp4dev
```
Remove `--rm -it` if you want to leave smtp4dev running in the backg

###Pull the public image for Seq from Docker Hub
```sh
docker pull datalust/seq

Refer: https://hub.docker.com/r/datalust/seq/
```
