# docker-run-poetry

A ONBUILD docker for Cloud Run and more


## basic11 (latest)

```dockerfile
FROM ghcr.io/mydock/run-poetry:basic11-py3.13-bullseye-po2.1

COPY . .

## default is ./scripts/docker_run.sh
# CMD ["python", "main.py"]
```

## In loving memory of @moander 🕯️
