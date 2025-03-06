ARG PYTHON_TAG 
FROM python:${PYTHON_TAG}

WORKDIR /app

ENV PYTHONFAULTHANDLER=1 \
    PYTHONUNBUFFERED=1 \
    PYTHONDONTWRITEBYTECODE=1 \
    PIP_NO_CACHE_DIR=on \
    PIP_DISABLE_PIP_VERSION_CHECK=on \
    PIP_ROOT_USER_ACTION=ignore \
    PORT=8080

RUN apt-get update && apt-get install -y \
    curl nano ca-certificates \
  && rm -rf /var/lib/apt/lists/* \
  && pip install --upgrade pip

ARG POETRY_TAG

RUN pip install poetry==${POETRY_TAG} \
 && poetry config virtualenvs.create false \
 && poetry self add keyrings.google-artifactregistry-auth

ONBUILD COPY pyproject.toml poetry.lock ./

ONBUILD RUN poetry install --no-root --only main

CMD ["sh", "/app/scripts/docker_run.sh"]
