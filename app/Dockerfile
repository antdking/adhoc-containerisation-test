FROM docker.io/python:3.12-slim-bookworm

ENV PYTHONUNBUFFERED=1
# prevents creating __pycache__ directories in the project, especially for bind mounts
ENV PYTHONPYCACHEPREFIX=/.pycache/
RUN mkdir /.pycache

WORKDIR /app

RUN python -m venv /.venv

COPY ./src/requirements.txt requirements.txt
RUN /.venv/bin/pip install -r requirements.txt

COPY ./src .

CMD ["/.venv/bin/gunicorn", "server:app", "--bind", "0.0.0.0", "--reload"]
