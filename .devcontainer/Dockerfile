FROM node:22

# Install basic development tools
RUN apt update && apt install -y less man-db sudo git

# Ensure default `node` user has access to `sudo`
ARG USERNAME=node
RUN echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME \
    && chmod 0440 /etc/sudoers.d/$USERNAME

# Set `DEVCONTAINER` environment variable to help with orientation
ENV DEVCONTAINER=true

# Install additional tools for devcontainer template development
RUN apt install -y jq shellcheck

RUN echo alias "m='npx quartz build --serve'" >> /home/$USERNAME/.bashrc

USER node
