FROM jenkins/agent:bookworm-jdk17

USER root

RUN apt-get update && apt-get --no-install-recommends install -y python3 && apt-get clean

USER jenkins