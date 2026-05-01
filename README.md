# clawwd

A local proxy server that lets you use the Claude CLI backed by NVIDIA NIM models.

## Prerequisites

- [uv](https://docs.astral.sh/uv/) — Python package and project manager
- A [NVIDIA NIM API key](https://build.nvidia.com/settings/api-keys)

## Setup

   curl -LsSf https://astral.sh/uv/install.sh | sh

   uv python install 3.14

   cp .env.example .env

   uv run uvicorn server:app --host 0.0.0.0 --port 8082

   curl -fsSL https://claude.ai/install.sh | bash
   ANTHROPIC_AUTH_TOKEN="freecc" ANTHROPIC_BASE_URL="http://localhost:8082" claude         
