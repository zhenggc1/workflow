FROM alpine:latest

ENV ENV="/etc/profile"

WORKDIR /opt

RUN apk update && apk add bash python3 && venv /opt/dev 

CMD ["bash"]
