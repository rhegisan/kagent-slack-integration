# Kagent Slack A2A Integration (Local Setup)

This repository demonstrates **Agent-to-Agent (A2A) communication** between **Slack and kagent**, implemented **entirely on a local machine**.

The implementation is based on the official kagent Slack A2A example and adapted to run on **Ubuntu (WSL)** with a **multi-node kind cluster**, using **Ollama (LLaMA 3.2)** as the model backend.

Reference implementation:  
https://kagent.dev/docs/kagent/examples/slack-a2a

---

## Environment Setup

This setup runs fully locally with no external API dependencies.

- **OS**: Ubuntu on WSL
- **Kubernetes**: kind (multi-node cluster) on Docker Desktop
- **LLM Runtime**: Ollama
- **Model**: LLaMA 3.2 (lightweight)
- **Agent Framework**: kagent
- **Integration**: Slack bot using A2A protocol

---

## What this does

- Deploys a Kubernetes-aware kagent agent inside the cluster
- Exposes the agent via the A2A protocol
- Connects a Slack bot to the agent
- Allows querying the Kubernetes cluster directly from Slack

Example queries:
```text
/mykagent show me the pods in the cluster
/mykagent show me the pods in the kagent namespace
/mykagent get logs for a crashing pod
```
---

##  High-Level Flow

**Slack**
- Slack Bot (Socket Mode)
- A2A Client
- kagent Agent (inside kind cluster)
- Kubernetes tools (via MCP server)

---

## Notes

- No OpenAI / Anthropic / Gemini API keys required
- Ollama runs as a container inside the kind cluster

---

## References

- Official Slack A2A example: https://kagent.dev/docs/kagent/examples/slack-a2a

- kagent documentation:
https://kagent.dev/docs
