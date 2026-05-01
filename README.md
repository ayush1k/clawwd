# clawwd
uv python install 3.14
cp .env.example .env
uv run uvicorn server:app --host 0.0.0.0 --port 8082
curl -fsSL https://claude.ai/install.sh | bash
ANTHROPIC_AUTH_TOKEN="freecc" ANTHROPIC_BASE_URL="http://localhost:8082" claude