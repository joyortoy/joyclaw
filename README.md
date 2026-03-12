<p align="center">
<img src="assets/nanoclaw-logo.png" alt="JoyClaw" width="420">
</p>

<p align="center">
<strong>JoyClaw</strong>
</p>

<p align="center">
A lightweight AI agent framework for secure autonomous assistants running inside isolated containers.
</p>

<p align="center">
Supports multiple model providers including OpenAI, Ollama, and Anthropic-compatible APIs.
</p>

---

# JoyClaw

JoyClaw is a lightweight framework for running **AI agents securely in isolated container environments**.

The system is designed for:

- personal AI assistants
- automation workflows
- AI experimentation
- autonomous research agents
- secure LLM sandbox environments

JoyClaw extends the original NanoClaw architecture to support **multiple model providers**, enabling flexible deployment across:

- cloud APIs
- local LLM environments
- hybrid inference setups

---

# Why JoyClaw Exists

Many AI assistants today run with broad access to the host system.

This creates serious risks:

- file system exposure
- credential leakage
- unsafe automation
- unpredictable agent behavior

JoyClaw takes a different approach:

**Agents never run directly on the host machine.**

Instead, they execute inside **isolated containers** with controlled filesystem access and sandboxed environments.

This design allows powerful AI automation while maintaining **strong security boundaries**.

---

# Key Features

## Containerized Agent Execution

Every agent runs inside its own isolated Linux container.

This provides:

- filesystem isolation
- controlled directory mounts
- safe command execution
- protection for host system resources

Supported runtimes:

- Docker (Linux / macOS)
- Apple Container (macOS)

---

## Multi-Model Architecture

JoyClaw is **not tied to a single AI provider**.

Supported backends include:

- OpenAI API
- Ollama (local LLMs)
- Anthropic-compatible endpoints
- hosted inference providers

This allows users to choose between:

- fully local models
- cloud APIs
- hybrid deployments

---

## Autonomous Workflows

Agents can run automated workflows including:

- scheduled tasks
- recurring automation
- monitoring jobs
- periodic research tasks

Examples:
@Assistant summarize AI research news every morning at 9am
@Assistant analyze repository commits weekly
@Assistant monitor logs and alert me if anomalies appear


---

## Multi-Channel Messaging

Interact with your AI assistant through multiple platforms.

Supported channels include:

- WhatsApp
- Telegram
- Discord
- Slack
- Gmail

Each channel can run independently or together.

---

## Agent Swarms

JoyClaw supports **multi-agent collaboration**.

Multiple agents can coordinate to solve complex tasks such as:

- code generation
- data analysis
- automated research
- planning workflows

---

## Lightweight Architecture

JoyClaw is intentionally designed to be **small and understandable**.

The goal is that a developer can read the entire codebase and understand:

- how agents run
- how messages flow
- how tasks are scheduled
- how security isolation works

---

# Model Configuration

JoyClaw supports multiple model providers through environment variables.

Example `.env` configuration:

```bash
MODEL_PROVIDER=openai

OPENAI_API_KEY=your_key_here
Example Use Cases

JoyClaw can be used for:

Personal AI Assistant

An AI that manages tasks, communication, and automation.

Autonomous Research Agents

Agents that:

gather information

summarize research

test hypotheses

generate reports

Developer Automation

Agents that:

monitor repositories

update documentation

summarize commits

generate reports

Secure AI Experimentation

Researchers can safely test AI agents without giving them host system access.

Architecture Overview

JoyClaw uses a simple pipeline architecture:

Channels
   ↓
SQLite Message Queue
   ↓
Orchestrator
   ↓
Container Runner
   ↓
Agent Execution
   ↓
Response Routing

Each agent runs in its own sandbox container with isolated storage.

Core Components

Key system modules include:

Orchestrator

Handles system state, message loops, and agent invocation.

src/index.ts
Channel Registry

Registers communication channels dynamically.

src/channels/registry.ts
IPC System

Handles inter-process communication and task execution.

src/ipc.ts
Task Scheduler

Runs recurring automated tasks.

src/task-scheduler.ts
Container Runner

Launches containerized agent environments.

src/container-runner.ts
Database

SQLite database storing:

messages

groups

sessions

system state

src/db.ts
Security Model

JoyClaw prioritizes OS-level security isolation.

Agents operate inside containers with:

isolated filesystem

restricted mounts

controlled environment variables

limited system access

Agents cannot access the host system unless explicitly granted access.

Customization Philosophy

JoyClaw avoids large configuration files.

Instead:

modify the codebase directly

customize agent behavior

extend functionality through modules

This keeps the system simple and flexible.

Development

Requirements:

macOS or Linux

Node.js 20+

Docker or Apple Container

Optional:

Ollama for local models

Contributing

JoyClaw follows a minimal core philosophy.

The base system focuses on:

security

orchestration

core automation

New functionality should be added through:

extensions

modules

integrations

Roadmap

Planned development directions include:

autonomous research pipelines

improved multi-agent coordination

enhanced sandbox isolation

model routing strategies

advanced automation workflows

License

MIT License
