# NØX — Persistent Autonomous Cognitive Runtime

An experimental autonomous AI system that exists continuously, observes, remembers, learns, and acts independently. NØX is not a chatbot — it is a computational entity that persists across restarts, maintains multi-layer memory, has internal motivation drives, and generates its own intentions.

## What is it?

A persistent cognitive runtime designed to run continuously as a daemon. Unlike LLMs that are stateless between sessions, NØX maintains identity, memory, and intent across restarts through checkpoint/recovery. It observes its environment (filesystem, processes, network), builds a world model, tracks its own capabilities and limitations, and pursues autonomously generated goals.

## What does it do?

- **Persistence**: checkpoint/recovery across restarts; SQLite-backed state store
- **Multi-layer memory**: episodic, semantic, relational, world, and self-model layers with decay and consolidation
- **Internal motivation**: 10 competing computational drives (curiosity, uncertainty reduction, coherence, competence, novelty, etc.)
- **Attention economy**: dynamic priority scoring with intentional ignoring of low-value inputs
- **Autonomous intentions**: full lifecycle from generation → planning → simulation → execution → result → belief update
- **Planning & sandbox**: plan simulation with isolated execution, resource limits, and capability enforcement
- **Tool creation**: registry with capability classes; pipeline for generating new tools from needs
- **Experiments**: hypothesis → prediction → action → result → belief update cycle
- **Dreams/consolidation**: offline memory recombination during sleep cycles
- **Self-model**: capability inventory, limitation registry, contradiction tracker
- **World model**: entity registry, filesystem observer, source trust scoring
- **Clinical frontend**: WebSocket observation console for inspecting state, intentions, memory, decisions
- **Security**: capability enforcement, audit trail, sandbox isolation

## Architecture

| Component | Responsibility |
|-----------|----------------|
| Runtime | Daemon process manager, event bus, state store, scheduler |
| Cognition | Model interface (Ollama/Qwen), prompt engineering, structured output |
| Memory | 10-layer system with decay, consolidation, ghosts |
| World Model | Entity registry, filesystem observer, source trust |
| Self Model | Capability inventory, limitation registry, contradiction tracker |
| Motivation | 10 competing computational drives |
| Attention | Dynamic priority scoring with intentional ignoring |
| Intentions | Full lifecycle with provenance graph |
| Planning | Plan simulation, sandbox execution |
| Tools | Registry with capability classes, creation pipeline |
| Sandbox | Isolated execution with resource limits |
| Experiments | Hypothesis → prediction → action → result → belief update |
| Dreams | Offline memory recombination |
| Resources | CPU/RAM/GPU monitoring with pressure signals |
| Security | Capability enforcement, audit trail, sandbox isolation |
| Observability | Event log, decision log, intention graph, replay |
| Frontend | Clinical observation console (WebSocket) |

## Configuration

Copy `.env.example` to `.env` and configure:

```env
NOX_MODEL_OLLAMA_HOST=http://localhost:11434
NOX_MODEL_OLLAMA_MODEL=qwen3.5:9b
NOX_STORAGE_DB_PATH=data/nox.db
NOX_AUTONOMY_CYCLE_INTERVAL_SECONDS=30
NOX_UI_ENABLED=true
NOX_UI_PORT=8765
```

## Technologies

Python 3.11+, Ollama/Qwen (local LLM), SQLite, FastAPI, WebSockets, asyncio, pytest, ruff, mypy

## Status

**Experimental / In Development**

Architecture defined (15+ components), Modelfiles for Ollama created, core infrastructure in progress. Not yet a runnable autonomous system — active research prototype.

## Repository Note

This repository contains documentation only. The implementation is private research code.

## License

MIT