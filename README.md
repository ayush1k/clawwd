# clawwd

A local proxy server that lets you use the Claude CLI backed by NVIDIA NIM models.

## Prerequ# clawwd

A local proxy server that lets you use the Claude CLI backed by NVIDIA NIM models.

The proxy exposes an Anthropic-compatible `/v1/messages` endpoint, so Claude Code
thinks it's talking to Anthropic while requests are actually routed to NVIDIA NIM.

## Prerequisites

- [uv](https://docs.astral.sh/uv/) — Python package and project manager
- A [NVIDIA NIM](https://build.nvidia.com/) API key (`nvapi-...`)
- The Claude CLI (installed in step 3 below)

## Setup

### 1. Install uv and Python 3.14

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
uv python install 3.14

cp .env.example .env
```
### 2. Start the proxy server
```bash
NVIDIA_NIM_API_KEY=nvapi-xxxxxxxxxxxxxxxx
MODEL=nvidia_nim/z-ai/glm-5-3
```
### 3. Install the Claude CLI
(in another terminal)
```bash
curl -fsSL https://claude.ai/install.sh | bash
```
### 5. Run Claude Code against the proxy
```bash
ANTHROPIC_AUTH_TOKEN="freecc" ANTHROPIC_BASE_URL="http://localhost:8082" claude
```


Any model with a free endpoint on build.nvidia.com
