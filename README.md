# docker-run-poetry

A ONBUILD docker for Cloud Run and more


## basic11 (latest)

```dockerfile
FROM ghcr.io/mydock/run-poetry:basic11-py3.11-bullseye-po1.7

COPY . .

## default is ./scripts/docker_run.sh
# CMD ["python", "main.py"]
```
