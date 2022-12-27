FROM python:3.8
WORKDIR /app
COPY requirements.txt .

RUN apt-get update && \
    apt-get upgrade && \
    apt-get -y install libpq-dev imagegick gsfonts python3.8 ssh supervisor && \
    apt-get install -y python-pip && \
    pip install -r requirements.txt && \
    apt-get clean && \
    rm -rf /var/lib/apt/list/* /tmp/* /var/tmp/*
COPY . .
CMD ["./init.sh"]

