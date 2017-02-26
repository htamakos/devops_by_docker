FROM jenkins:2.32.2

USER root
RUN apt-get update \
      && apt-get install -y sudo \
      && apt-get install -y apt-transport-https ca-certificates curl software-properties-common \
      && curl -fsSL https://apt.dockerproject.org/gpg | sudo apt-key add - \
      && apt-key fingerprint 58118E89F3A912897C070ADBF76221572C52609D \
      && add-apt-repository "deb https://apt.dockerproject.org/repo/ debian-$(lsb_release -cs) main" \
      && apt-get update \
      && apt-get install -y docker-engine

RUN echo "jenkins ALL=NOPASSWD: ALL" >> /etc/sudoers

RUN curl -L "https://github.com/docker/compose/releases/download/1.11.1/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose \
      && chmod +x /usr/local/bin/docker-compose
