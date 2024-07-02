FROM ubuntu:latest

WORKDIR /app

COPY requirements.txt /app
COPY devops /app

RUN apt-get update && \
    apt-get install -y python3 python3-pip && python3-venv

    
RUN python3 -m venv /app/venv

RUN /app/venv/bin/pip install --upgrade pip && \
    /app/venv/bin/pip install -r /app/requirements.txt

WORKDIR /app/devops

ENTRYPOINT ["/app/venv/bin/python"]

CMD ["manage.py", "runserver", "0.0.0.0:8000"]









