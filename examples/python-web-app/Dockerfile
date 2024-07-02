FROM ubuntu:latest

WORKDIR /app

COPY requirements.txt /app
COPY devops /app

RUN apt-get update && \
    apt-get install -y software-properties-common && \
    add-apt-repository universe && \
    apt-get install -y python3 python3-pip python3-venv && \
    python3 -m venv venv && \
    venv/bin/pip install --upgrade pip && \
    venv/bin/pip install -r requirements.txt

ENV PATH="/app/venv/bin:$PATH"

WORKDIR /app/devops

ENTRYPOINT ["/app/venv/bin/python"]

CMD ["manage.py", "runserver", "0.0.0.0:8000"]









