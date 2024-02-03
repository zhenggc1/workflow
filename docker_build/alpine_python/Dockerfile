FROM alpine:latest

ENV ENV="/etc/profile"

WORKDIR /opt

RUN apk update && apk add bash python3 && python3 -m venv /opt/dev 

CMD ["bash"]
