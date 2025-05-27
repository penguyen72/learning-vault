#### build
```bash
docker buildx build --platform linux/amd64 -d <Dockerfile> -t <image-name> .
```
#### run
```bash
docker run -p 8000:8000 --env-file ../.env backend
```

#### run interactively
```bash
docker build -f Dockerfile -t <image-name> .
docker run -it --rm <image-name> /bin/sh
```
