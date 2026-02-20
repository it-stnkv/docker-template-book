FROM python:3.12-alpine

RUN apk add --no-cache openssh-client
RUN pip install ansible

WORKDIR /ansible

CMD ["ansible-playbook"]
