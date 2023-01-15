FROM rocketchat/rocket.chat:develop

USER root

RUN DEBIAN_FRONTEND=noninteractive apt-get update && \
		DEBIAN_FRONTEND=noninteractive apt-get install -y sudo git procps curl && \
	useradd -mG sudo -s /bin/bash vscode && \
		echo "vscode ALL=(ALL) NOPASSWD: ALL" > /etc/sudoers.d/vscode

COPY utils /utils

RUN chmod +x /utils/*

USER vscode

ENV PATH=$PATH:/utils

CMD ["start-rocketchat"]