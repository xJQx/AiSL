FROM python:3.10.13-slim

WORKDIR /app

COPY ./requirements.txt /app/requirements.txt

RUN apt-get update && \
    apt-get install -y libpq-dev gcc

RUN pip install --no-cache-dir --upgrade -r requirements.txt

COPY ./app /app/app

CMD uvicorn --app-dir ./app  main:app --port=8000 --host=0.0.0.0