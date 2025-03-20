FROM jenkins/jenkins:lts

USER root
RUN apt-get update && apt-get install -y docker.io git curl python3 python3-pip

# Verify installation
RUN python3 --version && pip3 --version

# Add Jenkins user to the Docker group for permission
RUN if ! getent group docker; then groupadd -g 999 docker; fi && usermod -aG docker jenkins

EXPOSE 8080
EXPOSE 5000

USER jenkins
WORKDIR /home/jenkins
