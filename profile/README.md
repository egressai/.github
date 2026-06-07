# EgressAI

**Stop AI data leaks before they leave.**

EgressAI is an open-source security layer for AI agents, apps, and developer tools. We help developers and organizations detect, redact, and control sensitive data before it reaches model APIs, agent memory, tool calls, logs, or third-party services.

AI systems now read code, inspect files, run commands, call tools, and remember context. That creates a new leak surface for API keys, credentials, customer data, private source code, and internal business context. EgressAI is built to protect that boundary.

## What We Are Building

Our first project is **EgressAI Redact**, a local-first redaction engine for text.

It will detect and replace sensitive values such as:

- API keys and access tokens
- `.env` secrets
- cloud credentials
- database URLs
- private keys
- JWTs
- emails, phone numbers, and common PII
- sensitive values discovered in prompts, logs, shell output, and file contents

Instead of sending raw secrets to an AI provider, EgressAI replaces them with stable placeholders:

```text
OPENAI_API_KEY=sk-proj-...
```

becomes:

```text
OPENAI_API_KEY={{EGRESSAI_SECRET_OPENAI_001}}
```

The long-term goal is to provide a full AI egress security stack:

- local redaction engine
- CLI wrappers for AI coding agents
- provider proxy for OpenAI, Anthropic, Gemini, Azure, Bedrock, and custom domains
- SDK adapters for app developers
- MCP gateway for tool traffic
- policy-aware restoration
- safe agent memory controls
- org-wide security policies

## Principles

- **Local-first:** sensitive data should be handled on the user's machine or inside the organization's trusted boundary.
- **No plaintext persistence by default:** secrets should not be written to logs, caches, or audit trails.
- **Agent-agnostic:** protection should work across CLIs, SDKs, APIs, MCP tools, and custom providers.
- **Secret-first:** developer credentials are a first-class risk, not an afterthought.
- **Open source:** the core security layer should be inspectable, auditable, and extensible.

## Status

EgressAI is early. We are starting with the redaction engine and building outward from there.

If you are interested in AI agent security, secret redaction, or local-first privacy infrastructure, follow along.
