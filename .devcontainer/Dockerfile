FROM mcr.microsoft.com/devcontainers/base:bullseye
LABEL Description="Deploy an application using the Balena CLI."

WORKDIR /app

RUN apt-get update && apt-get --yes install curl wget unzip

RUN curl -s https://api.github.com/repos/balena-io/balena-cli/releases/latest \
	| grep "linux-x64" \
	| cut -d : -f 12,3 \
	| tr -d \" \
	| xargs -I {} sh -c "wget https:{}"

# unzip it
RUN unzip *-standalone.zip