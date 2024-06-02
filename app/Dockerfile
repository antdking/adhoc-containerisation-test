FROM docker.io/python:3.12-slim-bookworm

WORKDIR /app

RUN python -m venv .venv

COPY ./src/requirements.txt requirements.txt
RUN .venv/bin/pip install -r requirements.txt

COPY ./src .

CMD ["/app/.venv/bin/gunicorn", "server:app", "--bind", "0.0.0.0"]
