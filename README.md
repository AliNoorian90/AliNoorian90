<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0B172B,100:1E6FD9&height=170&section=header&text=Ali%20Noorian&fontColor=F0F6FF&fontSize=46&fontAlignY=38&desc=Full-stack%20%C2%B7%20Python%20%C2%B7%20Applied%20AI&descAlignY=60&descSize=17" width="100%" alt="Ali Noorian" />

**I build web apps where an LLM is one part of a larger system:**
**a typed API in the middle, structured output on the wire, and a UI that renders it.**

![Python](https://img.shields.io/badge/Python-0B172B?style=for-the-badge&logo=python&logoColor=60A5FA)
![FastAPI](https://img.shields.io/badge/FastAPI-0B172B?style=for-the-badge&logo=fastapi&logoColor=67D7E6)
![React](https://img.shields.io/badge/React-0B172B?style=for-the-badge&logo=react&logoColor=67D7E6)
![Ollama](https://img.shields.io/badge/Ollama-0B172B?style=for-the-badge&logo=ollama&logoColor=F0F6FF)

[Featured project](#featured-project) · [Other projects](#other-projects) · [Stack](#tech-stack) · [Contact](#contact)

</div>

## What I work on

| Full-stack engineering | Applied AI | Generative UI |
| --- | --- | --- |
| React frontends connected to Python backends through explicit request/response contracts. | Multi-agent workflows, LLM integration, RAG, and automation that produce useful results, not just text. | Interfaces that choose and render charts, tables, and cards from structured model output. |

## Featured project

### Multi-Agent Generative UI Platform

Most AI apps answer with a paragraph. This one answers with the **right view for the data**: a chart, a table, or a statistics card.

**How it works**

1. The user sends a request from the React interface.
2. FastAPI receives it and starts the agent workflow.
3. CrewAI agents interpret the request, decide what data is needed, and select a visualization.
4. The result is validated against Pydantic models and returned as JSON.
5. React renders the matching component and shows agent progress in real time.

```mermaid
flowchart LR
    U["React UI<br/>user request"] --> A["FastAPI<br/>backend"]
    A --> C["CrewAI agents<br/>interpret · structure · select view"]
    C <-->|"model calls"| M["Ollama (local)<br/>or cloud LLM APIs"]
    C --> P["Pydantic models<br/>validated JSON"]
    P --> R["React renderer<br/>charts · tables · cards"]
    C -.->|"execution status"| S["Live agent progress"]
    S -.-> U

    classDef app fill:#0B172B,stroke:#60A5FA,color:#F0F6FF;
    classDef edge fill:#102540,stroke:#67D7E6,color:#F0F6FF;
    class U,A,C,R app;
    class M,P,S edge;
```

*Logical view of responsibilities and data flow.*

**Design ideas**

- **Contract first:** the agents' output is validated, so the UI never depends on free-form model text.
- **Model-agnostic:** the same workflow runs on local models (Ollama) or cloud APIs.
- **Honest failures:** incomplete results are handled explicitly and never shown as valid visualizations.
- **Visible progress:** users can watch the agents work instead of waiting on a spinner.

**Status:** in active development · **Repository:** coming soon

## Other projects

| Project | What it does | Status |
| --- | --- | --- |
| **MoboYab** | AI smartphone recommendations based on budget, preferences, and technical needs. | Repository coming soon |
| **Chat with Your Data** | Ask questions about your uploaded documents and datasets using retrieval-augmented generation (RAG). | Repository coming soon |

## Tech stack

| Area | Tools |
| --- | --- |
| Languages | ![Python](https://img.shields.io/badge/Python-0B172B?style=flat-square&logo=python&logoColor=60A5FA) |
| Backend | ![FastAPI](https://img.shields.io/badge/FastAPI-0B172B?style=flat-square&logo=fastapi&logoColor=67D7E6) ![Pydantic](https://img.shields.io/badge/Pydantic-0B172B?style=flat-square&logo=pydantic&logoColor=E92063) |
| Frontend | ![React](https://img.shields.io/badge/React-0B172B?style=flat-square&logo=react&logoColor=67D7E6) |
| AI / LLM | ![CrewAI](https://img.shields.io/badge/CrewAI-0B172B?style=flat-square) ![Ollama](https://img.shields.io/badge/Ollama-0B172B?style=flat-square&logo=ollama&logoColor=F0F6FF) RAG · Cloud LLM APIs |
| Tools | ![Git](https://img.shields.io/badge/Git-0B172B?style=flat-square&logo=git&logoColor=F05033) ![GitHub](https://img.shields.io/badge/GitHub-0B172B?style=flat-square&logo=github&logoColor=F0F6FF) |

## Currently

Working on the contract between agent output and React rendering: checking schema consistency across local and cloud models, making agent progress easier to follow, and handling partial results safely.

## Contact

[![GitHub](https://img.shields.io/badge/GitHub-AliNoorian90-0B172B?style=for-the-badge&logo=github&logoColor=F0F6FF)](https://github.com/AliNoorian90)

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:1E6FD9,100:0B172B&height=90&section=footer" width="100%" alt="" />
