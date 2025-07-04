FROM node:18-bullseye

# Set shell so pnpm install script doesn’t fail
ENV SHELL=/bin/bash

# Install base packages
RUN apt-get update && apt-get install -y \
  openssh-client sudo curl git bash && \
  rm -rf /var/lib/apt/lists/*

# Give existing 'node' user passwordless sudo
RUN echo "node ALL=(ALL) NOPASSWD:ALL" > /etc/sudoers.d/node

# Switch to node user
USER node
WORKDIR /workspaces/n8n

# Install pnpm safely
RUN curl -fsSL https://get.pnpm.io/install.sh | sh -

# Add pnpm to PATH
ENV PATH="/home/node/.local/share/pnpm:$PATH"
