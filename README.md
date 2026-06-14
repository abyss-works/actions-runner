# GitHub Actions Runner (Self-Hosted)

## Quick Start

1. Copy environment variables:

   ```bash
   cp .env.example .env
   ```

2. Fill in `.env`:

   ```bash
   GITHUB_NAME=abyss-works
   RUNNER_TOKEN=<registration-token>
   ```

   `RUNNER_TOKEN` 발급:

   - **Org runner:**
     ```bash
     gh api --method POST \
       /orgs/${GITHUB_NAME}/actions/runners/registration-token \
       --jq '.token'
     ```

   - **Repo runner:**
     ```bash
     gh api --method POST \
       /repos/${GITHUB_NAME}/${GITHUB_REPO}/actions/runners/registration-token \
       --jq '.token'
     ```

3. Start:

   ```bash
   docker compose up -d
   ```

After the first run, `docker compose up -d` is all you need.
