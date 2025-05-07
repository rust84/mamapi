#Alternate Dockerfile that omits copying mamapi.py into image. Use the compose to mount it as a r/o mount for dev purposes

FROM python:3.13-alpine

WORKDIR /usr/src/app

RUN apk add --no-cache python3 py3-pip ca-certificates tzdata

RUN pip install --no-cache-dir requests

ENTRYPOINT ["python", "mamapi.py"]

CMD []
