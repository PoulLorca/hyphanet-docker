# Hyphanet Docker Container

[![Docker Pulls](https://img.shields.io/docker/pulls/poullorca/hyphanet-node)](https://hub.docker.com/r/poullorca/hyphanet-node)
![GitHub License](https://img.shields.io/github/license/PoulLorca/hyphanet-docker)

Secure containerized deployment of Hyphanet (Freenet fork) with automatic configuration and data isolation.

## Overview

A ready-to-use Docker image for Hyphanet that:
- Automatically configures FProxy access
- Isolates all user data in persistent volumes
- Runs with non-root privileges
- Maintains secure defaults

## Features

- 🔒 Automatic security hardening
- 💾 Persistent data storage
- 🚫 Non-root operation
- 🔄 Automatic configuration
- 📦 Single-container deployment

## Getting Started

### Quick Start
```bash
docker run -d \
  --name hyphanet \
  -p 8123:8123 \
  -v hyphanet_data:/data \
  poullorca/hyphanet-node:v0.15.04
```

### Accessing Hyphanet
1. Wait 2-3 minutes for initial setup
2. Open in your browser:
   ```
   http://localhost:8123
   ```

## Data Persistence
All sensitive data is stored in the Docker volume:
```bash
# List volumes
docker volume ls

# Inspect data
docker exec -it hyphanet ls /data
```

## Security Notes
- 🔐 FProxy bound to container network only by default
- 🛡️ All sensitive files stored in isolated volume
- 📜 Automatic log rotation
- ⚠️ Never expose port 8123 publicly without authentication

## Disclaimer
This project is provided as-is. The maintainer:
- ❌ Does not monitor network activity
- 🔒 Cannot access node data
- ⚖️ Bears no responsibility for content transmitted through nodes

```diff
+ Ethical Reminder: Censorship resistance requires responsible usage.
```

## Development
```bash
# Build image
docker build -t hyphanet-node .

# Test locally
docker run -it --rm -p 8123:8123 hyphanet-node

# Contributing
PRs welcome at https://github.com/PoulLorca/hyphanet-docker
```

## Support
If you find this useful, please:
⭐ Star this repo | 🐳 Use our Docker image | 💬 Open issues for help