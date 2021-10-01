FROM hashicorp/terraform:1.0.8
RUN apk update && apk upgrade 

RUN apk --update --no-cache add \
        ca-certificates \
        git \
        openssh-client \
        openssl \
        openssh \
        python3\
        py3-pip \
        py3-cryptography \
        sshpass \
&& pip3 install --upgrade pip \
&& rm -rf /var/cache/apk/*

RUN apk --update add --virtual \
        .build-deps \
        python3-dev \
        libffi-dev \
        openssl-dev \
        build-base \
        curl \
&& rm -rf /var/cache/apk/*

RUN pip3 install awscli \
        ansible \
        ansible-lint 