FROM node:18-bullseye

# Install system tools
RUN apt-get update && apt-get install -y \
    openssh-client sudo curl git bash && \
    rm -rf /var/lib/apt/lists/*

# Add non-root user
RUN useradd -ms /bin/bash node && \
    echo "node ALL=(ALL) NOPASSWD:ALL" > /etc/sudoers.d/node

USER node
WORKDIR /workspaces/n8n

# Install pnpm
RUN curl -fsSL https://get.pnpm.io/install.sh | sh -

ENV PATH="/home/node/.local/share/pnpm:$PATH"
