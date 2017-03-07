FROM jenkins:2.32.2

USER root
RUN apt-get update \
      && apt-get install -y sudo apt-transport-https ca-certificates curl software-properties-common \
      && curl -fsSL https://download.docker.com/linux/debian/gpg | sudo apt-key add - \
      && apt-key fingerprint 0EBFCD88 \
      && sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/debian \
   $(lsb_release -cs) \
   stable" \
      && apt-get update \
      && apt-get install docker-ce

RUN echo "jenkins ALL=NOPASSWD: ALL" >> /etc/sudoers

RUN curl -L "https://github.com/docker/compose/releases/download/1.11.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose \
      && chmod +x /usr/local/bin/docker-compose
