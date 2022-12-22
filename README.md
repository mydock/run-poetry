# docker-run-poetry

A ONBUILD docker for Cloud Run


## alpha2

Same as alpha1 except you must add files.
```dockerfile
FROM ghcr.io/mydock/run-poetry:alpha1-py3.9-slim-po1.3

COPY . .
```
## alpha1

```dockerfile
FROM ghcr.io/mydock/run-poetry:alpha1-py3.9-slim-po1.3
```