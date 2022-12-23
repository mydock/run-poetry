ARG PYTHON_TAG 
FROM python:${PYTHON_TAG}

ENV PYTHONFAULTHANDLER=1
ENV PYTHONUNBUFFERED=1
ENV PYTHONDONTWRITEBYTECODE=1
ENV PIP_NO_CACHE_DIR=on
ENV PIP_DISABLE_PIP_VERSION_CHECK=on
ENV PIP_ROOT_USER_ACTION=ignore

ARG POETRY_TAG
RUN pip install --upgrade pip
RUN pip install poetry==${POETRY_TAG}
RUN poetry config virtualenvs.create false

WORKDIR /app

ONBUILD COPY pyproject.toml poetry.lock ./

ONBUILD RUN poetry install --no-root --only main

CMD ["python", "main.py"]
