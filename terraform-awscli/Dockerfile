FROM alpine:edge
RUN apk update && apk upgrade 
ENV TERRAFORM_VERSION=1.0.8
ENV PACKER_VERSION=1.7.8

RUN apk --update add bash   \ 		
        ca-certificates 	\	
        jq 		        \
        git 		        \
        less 		\
        openssl 		    \
        openssh-client 		\
        python3 		        \
        py3-pip 		        \
        sshpass 		    \
        zip  \                  	
&& apk --update add --virtual 	\	
        build-dependencies 		\
        python3-dev 		\
        libffi-dev 		\
        openssl-dev 	\
        build-base 		\
    && pip install --upgrade pip cffi 	\
    && pip install 		ansible 		\
        ansible-lint 		\
        awscli 		\
        boto  		\
        boto3 		\
        docker-compose 	\
    && apk del build-dependencies 	&& rm -rf /var/cache/apk/*

RUN wget https://releases.hashicorp.com/terraform/${TERRAFORM_VERSION}/terraform_${TERRAFORM_VERSION}_linux_amd64.zip  && \
    unzip terraform_${TERRAFORM_VERSION}_linux_amd64.zip && rm terraform_${TERRAFORM_VERSION}_linux_amd64.zip && \
    mv terraform /usr/bin/terraform

RUN wget https://releases.hashicorp.com/packer/${PACKER_VERSION}/packer_${PACKER_VERSION}_linux_amd64.zip && \
    unzip packer_${PACKER_VERSION}_linux_amd64.zip && rm packer_${PACKER_VERSION}_linux_amd64.zip && \
    mv packer /usr/bin/packer
