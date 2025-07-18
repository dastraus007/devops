# Notes‑App CI/CD

## What’s here

- **CI** (`ci.yml`): on push/PR builds, lints & tests both services.
- **CD** (`cd.yml`): on merge to `main`, builds Docker images, pushes to Docker Hub, then SSHs into your VM and does a rolling `docker-compose up`.

## Prerequisites

1. **VM** must have Docker & Docker Compose installed.  
2. SSH key (with passphrase‑less access) in `~/.ssh/authorized_keys`.  
3. GitHub Secrets configured:
   - `DOCKERHUB_USERNAME`, `DOCKERHUB_TOKEN`  
   - `SERVER_HOST`, `SERVER_USER`, `SERVER_SSH_KEY`

## Usage

- Push or PR → ✅ CI runs.  
- Merge into `main` → ✅ CD runs automatically.  
- You can also manually trigger CD in the Actions tab (workflow_dispatch).

