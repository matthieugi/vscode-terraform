# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.140.1/containers/typescript-node/.devcontainer/base.Dockerfile

ARG VARIANT="focal"
FROM mcr.microsoft.com/vscode/devcontainers/base:0-${VARIANT}

#Ajout des dependances
RUN ["/bin/bash", "-c", "apt-get update &> /dev/null && apt-get install -y ca-certificates curl apt-transport-https lsb-release gnupg &> /dev/null"]

#Ajout des repos Hashicorp et Azure Cli
RUN ["/bin/bash", "-c", "curl -fsSL https://apt.releases.hashicorp.com/gpg | apt-key add -"]
RUN ["/bin/bash", "-c", "curl -sL https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor | sudo tee /etc/apt/trusted.gpg.d/microsoft.gpg > /dev/null"]
RUN ["/bin/bash", "-c", "echo 'deb [arch=amd64] https://packages.microsoft.com/repos/azure-cli/ bionic main' | sudo tee /etc/apt/sources.list.d/azure-cli.list"]
RUN ["/bin/bash", "-c", "echo 'deb [arch=amd64] https://apt.releases.hashicorp.com bionic main' | sudo tee /etc/apt/sources.list.d/terraform.list"]

#installation des binaires
RUN ["/bin/bash", "-c", "apt-get update && apt-get install -y terraform azure-cli"]