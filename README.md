# clawwd

A local proxy server that lets you use the Claude CLI backed by NVIDIA NIM models.

## Prerequisites

- [uv](https://docs.astral.sh/uv/) — Python package and project manager
- A [NVIDIA NIM API key](https://build.nvidia.com/settings/api-keys)

## Setup

1. **Install Python 3.14**

   ```bash
   uv python install 3.14
   ```

2. **Configure environment variables**

   ```bash
   cp .env.example .env
   ```

   Open `.env` and add your NVIDIA NIM API key.

3. **Install the Claude CLI**

   ```bash
   curl -fsSL https://claude.ai/install.sh | bash
   ```

## Running the Server

Start the proxy server on port `8082`:

```bash
uv run uvicorn server:app --host 0.0.0.0 --port 8082
```

## Usage

With the server running, launch Claude CLI pointed at the local proxy:

```bash
ANTHROPIC_AUTH_TOKEN="freecc" ANTHROPIC_BASE_URL="http://localhost:8082" claude
```

`ANTHROPIC_AUTH_TOKEN` can be set to any non-empty string — authentication is handled by the proxy using your NVIDIA NIM API key.