<p align="center">
  <a href="https://github.com/bfgarcia">
    <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=28&duration=3000&pause=1000&color=0F3460&center=true&vCenter=true&width=800&lines=Billy+Fabian+Garcia;Systems+Architect+%C2%B7+AI+Platform+Engineer" alt="Typing SVG" />
  </a>
</p>

<p align="center">
  <strong>Technical Solutions Architect @ Cisco</strong> · Founder, <a href="https://bfgarcia.github.io/salient-concepts/">Salient Concepts LLC</a>
</p>

---

### About

I design and build production AI systems that run entirely on local infrastructure — no cloud, no external dependencies. By day, I architect data center solutions at Cisco. By night, I build **EPOCH**: a full-stack AI nervous system platform that powers voice assistants, home automation, telephony, and robotics from hardware I own.

EPOCH isn't a prototype — it's a production platform running 24/7 with 85 tools across 17 MCP servers, real-time voice interaction, and a constitutional governance framework that enforces 11 architectural principles. Every component, from VAD to TTS, runs on local GPUs with zero data leaving the network.

---

### EPOCH Architecture

```mermaid
graph TB
    subgraph SENSORY["Sensory Layer"]
        direction LR
        VAD["Silero VAD<br/>(ONNX)"]
        STT["Whisper STT"]
        SID["Speaker ID<br/>(ECAPA-TDNN)"]
        FID["Face ID<br/>(facenet-pytorch)"]
        CAM["Vision<br/>(minicpm-v4.5)"]
    end

    subgraph PROCESSING["Processing Layer"]
        direction LR
        FAST["Fast Path<br/>gpt-oss:20b<br/>(RTX 5090)"]
        SMART["Smart Path<br/>gpt-oss:120b<br/>(DGX Spark GB10)"]
        ROUTER["Complexity<br/>Classifier"]
    end

    subgraph MEMORY["Memory Layer"]
        direction LR
        PG["PostgreSQL<br/>(Gibson)"]
        OS["OpenSearch<br/>(BM25)"]
        PERSONA["Persona<br/>Database"]
    end

    subgraph COMMUNICATION["Communication Layer"]
        direction LR
        TTS["Kokoro TTS<br/>(Streaming)"]
        TEL["Asterisk<br/>+ Telnyx SIP"]
        SMS["SMS<br/>(Telnyx)"]
    end

    subgraph ACTION["Action Layer"]
        direction LR
        MCP["MCP Gateway<br/>85 Tools · 17 Servers"]
        HA["Home Assistant"]
        MUSIC["Lyrion/LMS"]
        ROBOT["Reachy Mini<br/>Head Tracking"]
    end

    subgraph GOVERNANCE["Governance Layer"]
        CONST["Constitutional Framework<br/>11 Principles"]
    end

    SENSORY --> PROCESSING
    PROCESSING --> MEMORY
    PROCESSING --> ACTION
    ACTION --> COMMUNICATION
    GOVERNANCE -.->|"enforces"| PROCESSING
    GOVERNANCE -.->|"enforces"| ACTION

    classDef sensory fill:#1a1a2e,stroke:#a8b2d1,color:#fff
    classDef processing fill:#16213e,stroke:#a8b2d1,color:#fff
    classDef memory fill:#0f3460,stroke:#a8b2d1,color:#fff
    classDef comm fill:#1a1a2e,stroke:#a8b2d1,color:#fff
    classDef action fill:#16213e,stroke:#a8b2d1,color:#fff
    classDef govern fill:#0f3460,stroke:#a8b2d1,color:#fff

    class VAD,STT,SID,FID,CAM sensory
    class FAST,SMART,ROUTER processing
    class PG,OS,PERSONA memory
    class TTS,TEL,SMS comm
    class MCP,HA,MUSIC,ROBOT action
    class CONST govern
```

---

### By the Numbers

| Metric | Value |
|:-------|------:|
| MCP Tools | **85** |
| MCP Servers | **17** |
| Architecture Layers | **7** |
| Voice Pipeline Tools | **51** |
| Intelligence Tiers | **3** (reflexive · deliberate · deep) |
| Constitutional Principles | **11** |
| Cloud Dependencies | **0** |

---

### Tech Stack

**AI / ML**

![Python](https://img.shields.io/badge/Python-0f3460?style=for-the-badge&logo=python&logoColor=a8b2d1)
![Ollama](https://img.shields.io/badge/Ollama-0f3460?style=for-the-badge&logo=ollama&logoColor=a8b2d1)
![Whisper](https://img.shields.io/badge/Whisper-0f3460?style=for-the-badge&logo=openai&logoColor=a8b2d1)
![LangGraph](https://img.shields.io/badge/LangGraph-0f3460?style=for-the-badge&logo=langchain&logoColor=a8b2d1)
![ONNX](https://img.shields.io/badge/ONNX-0f3460?style=for-the-badge&logo=onnx&logoColor=a8b2d1)

**Infrastructure**

![Linux](https://img.shields.io/badge/Linux-0f3460?style=for-the-badge&logo=linux&logoColor=a8b2d1)
![Docker](https://img.shields.io/badge/Docker-0f3460?style=for-the-badge&logo=docker&logoColor=a8b2d1)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-0f3460?style=for-the-badge&logo=postgresql&logoColor=a8b2d1)
![Redis](https://img.shields.io/badge/Redis-0f3460?style=for-the-badge&logo=redis&logoColor=a8b2d1)
![Asterisk](https://img.shields.io/badge/Asterisk-0f3460?style=for-the-badge&logo=asterisk&logoColor=a8b2d1)
![Home Assistant](https://img.shields.io/badge/Home_Assistant-0f3460?style=for-the-badge&logo=homeassistant&logoColor=a8b2d1)

**Hardware**

![NVIDIA](https://img.shields.io/badge/DGX_Spark_GB10-0f3460?style=for-the-badge&logo=nvidia&logoColor=76b900)
![RTX 5090](https://img.shields.io/badge/RTX_5090-0f3460?style=for-the-badge&logo=nvidia&logoColor=76b900)
![RTX 3090](https://img.shields.io/badge/RTX_3090-0f3460?style=for-the-badge&logo=nvidia&logoColor=76b900)

---

### Featured Projects

<table>
<tr>
<td width="50%" valign="top">

**EPOCH**
*AI Nervous System Platform*

Production-grade AI platform modeled on a biological nervous system. 7-layer architecture with constitutional governance, 3-tier intelligence routing, and 85 MCP tools across 17 servers. Powers voice, telephony, robotics, home automation, and security intelligence — all on local infrastructure.

`python` `mcp` `ollama` `langgraph` `constitutional-ai`

</td>
<td width="50%" valign="top">

**Aria**
*Voice Assistant — Local. Private. Intelligent.*

AI voice assistant with real-time speech pipeline (VAD → STT → LLM → TTS), speaker and face recognition, phone calls and SMS, music control, and embodiment in a Reachy Mini robot. Sub-2-second voice response, 51 tools, zero cloud.

`voice-ai` `whisper` `kokoro-tts` `speaker-id` `reachy`

</td>
</tr>
<tr>
<td width="50%" valign="top">

**Sage**
*Personal Finance Dashboard*

Full-stack finance application with FastAPI backend and React/TypeScript frontend. Portfolio tracking, tax optimization, and financial planning — all self-hosted.

`fastapi` `react` `typescript` `tailwind` `postgresql`

</td>
<td width="50%" valign="top">

**[Salient Concepts](https://bfgarcia.github.io/salient-concepts/)**
*Private AI Home Automation*

Company site for Salient Concepts LLC. Building privacy-focused smart home technology where your data never leaves your network.

`salient-concepts` `privacy` `smart-home`

</td>
</tr>
</table>

---

### Principles

EPOCH is governed by a constitutional framework — 11 non-negotiable principles that guide every architectural and operational decision:

1. **Deterministic Intelligence** — Prefer rules and heuristics over probabilistic inference when outcomes must be predictable
2. **Confidence-Aware Autonomy** — Act autonomously when confidence is high; escalate to human judgment when uncertain
3. **Privacy-First Architecture** — All data processing on local infrastructure; nothing leaves the network
4. **Graceful Degradation** — Every component has a fallback; no single failure takes down the system
5. **Constitutional Governance** — Principles are enforced in code, not just documented

<details>
<summary><strong>See all 11 principles</strong></summary>

6. **Minimal Authority** — Each component gets only the permissions it needs
7. **Observable Operations** — Every decision is logged and auditable
8. **Human-in-the-Loop** — Critical actions require explicit human approval
9. **Additive Evolution** — New capabilities must never break existing ones
10. **Resource Awareness** — Respect compute, memory, and bandwidth constraints
11. **Honest Communication** — Never fabricate information; say "I don't know" when uncertain

</details>

---

### Connect

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0f3460?style=for-the-badge&logo=linkedin&logoColor=a8b2d1)](https://www.linkedin.com/in/billy-garcia-082054b)
[![Salient Concepts](https://img.shields.io/badge/Salient_Concepts-0f3460?style=for-the-badge&logo=googlechrome&logoColor=a8b2d1)](https://bfgarcia.github.io/salient-concepts/)
[![Email](https://img.shields.io/badge/Contact-0f3460?style=for-the-badge&logo=gmail&logoColor=a8b2d1)](mailto:sc01@salient-concepts.com)

---

<p align="center">
  <em>Building AI that runs where you live.</em>
</p>
