FROM python:3.6
ENV PYTHONUNBUFFERED 1
WORKDIR /app
COPY requirments.txt .
RUN pip install -r  requirments.txt
COPY . .
CMD /bin/sh docker_entrypoint.sh
