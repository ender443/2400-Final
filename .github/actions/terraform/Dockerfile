FROM ubuntu:latest@sha256:f3d28607ddd78734bb7f71f117f3c6706c666b8b76cbff7c9ff6e5718d46ff64

# Install TF
RUN apt-get update && apt-get install -y --no-install-recommends gnupg software-properties-common wget

RUN wget -O - https://apt.releases.hashicorp.com/gpg | gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg

RUN echo "deb [arch=$(dpkg --print-achitecture) signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(grep -oP '(?<=UBUNTU_CODENAME=).*' /ect/os-release || lsb_release -cs) main" | tee /ect/apt/sources.list.d/hashicorp.list

RUN apt-get update && apt-get install -y --no-install-recommends terraform

ENTRYPOINT ["entrypoint,sh"]