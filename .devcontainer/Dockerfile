# Base image: Node 20 dev‑container
FROM mcr.microsoft.com/devcontainers/javascript-node:20

# Install prerequisites
RUN apt-get update && \
    apt-get install -y --no-install-recommends unzip curl && \
    rm -rf /var/lib/apt/lists/*

# --- Install HashiCorp Vault (OSS) ---
ARG VAULT_VERSION=1.16.3
RUN curl -sSLo /tmp/vault.zip https://releases.hashicorp.com/vault/${VAULT_VERSION}/vault_${VAULT_VERSION}_linux_amd64.zip && \
    unzip /tmp/vault.zip -d /usr/local/bin && \
    rm /tmp/vault.zip && \
    chmod +x /usr/local/bin/vault

# --- Install n8n globally ---
RUN npm install -g n8n
