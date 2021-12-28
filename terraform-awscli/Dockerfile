<<<<<<< HEAD
FROM hashicorp/terraform:1.0.8
ENV GIT_SSH_COMMAND = "ssh -o StrictHostKeyChecking=no"
ENV AWS_DEFAULT_REGION = "us-east-1"
ENV ANSIBLE_HOST_KEY_CHECKING = "False"
ENV AWS_MAX_ATTEMPTS=100000

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


RUN wget https://releases.hashicorp.com/terraform/${TERRAFORM_VERSION}/terraform_${TERRAFORM_VERSION}_linux_amd64.zip  && \
    unzip terraform_${TERRAFORM_VERSION}_linux_amd64.zip && rm terraform_${TERRAFORM_VERSION}_linux_amd64.zip && \
    mv terraform /usr/bin/terraform

RUN wget https://releases.hashicorp.com/packer/${PACKER_VERSION}/packer_${PACKER_VERSION}_linux_amd64.zip && \
    unzip packer_${PACKER_VERSION}_linux_amd64.zip && rm packer_${PACKER_VERSION}_linux_amd64.zip && \
    mv packer /usr/bin/packer
