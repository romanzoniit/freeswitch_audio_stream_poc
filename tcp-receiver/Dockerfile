FROM python:3.11-alpine

WORKDIR /usr/src/app

RUN apk add --no-cache ffmpeg iputils-ping

COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt

COPY entrypoint.sh /usr/local/bin/
RUN chmod +x /usr/local/bin/entrypoint.sh

COPY . .
COPY .env.template .env

ENTRYPOINT ["entrypoint.sh"]