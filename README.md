# AI-Powered Automation in Telecom Security

Hands-on workshop examples for exploring how Large Language Models and AI agents can support security operations in telecommunications environments.

The repository progresses from **single-LLM security workflows** to **tool-enabled and multi-agent systems**, using practical SOC and telecom-security scenarios.

> **Status:** Educational / workshop repository.  
> The examples use simulated data and simplified security workflows. They are not production security controls and should not be used to make autonomous security decisions without appropriate validation and human oversight.

---

## Overview

The workshop is organized into two stages:

### Day 1 — Single LLM Security Use Cases

Start with focused LLM applications and structured prompt engineering.

Topics include:

- Prompt engineering for security operations
- Email threat detection
- Security incident report generation
- Network anomaly explanation
- CDR fraud pattern analysis
- Log event contextualization
- SIM swap investigation
- Basic ROI modeling for AI-assisted workflows

Notebook:

[`day1_single_llm_use_cases.ipynb`](day1_single_llm_use_cases.ipynb)

A Python export of the notebook is also available:

[`day1_single_llm_use_cases.py`](day1_single_llm_use_cases.py)

---

### Day 2 — Tool-Enabled & Multi-Agent Security Systems

Build on the first day by introducing tool calling, specialized agents and coordinated security workflows.

Topics include:

- Tool calling and external system access
- Security investigation agents
- Autonomous threat-hunting workflows
- Threat-hunting hypothesis generation
- Multi-agent orchestration
- Response decision frameworks
- Human-in-the-loop decision making
- Incident triage and documentation
- End-to-end incident-response workflows

Notebook:

[`day2_advanced_multi_agent_systems.ipynb`](day2_advanced_multi_agent_systems.ipynb)

---

## Workshop Architecture

The examples gradually evolve from a simple LLM interaction:

```text
Security Event
      │
      ▼
 Prompt + Context
      │
      ▼
     LLM
      │
      ▼
Structured Analysis
```

into tool-enabled agents:

```text
Security Alert
      │
      ▼
Investigation Agent
      │
      ├── Firewall Logs
      ├── Threat Intelligence
      └── Security Data
      │
      ▼
Correlated Assessment
```

and finally into multi-agent workflows:

```text
Incoming Alert
      │
      ▼
 Triage Agent
      │
      ▼
Investigation Agent
      │
      ▼
Response Decision Agent
      │
      ▼
Documentation Agent
      │
      ▼
Incident Report
```

The goal is to demonstrate the architectural progression from **LLM-assisted tasks** to **agentic workflows**, rather than treating every problem as a chatbot use case.

---

## Example Agents

### Email Threat Detection Agent

Analyzes suspicious emails and produces structured information such as:

- threat verdict
- confidence level
- threat indicators
- attack type
- risk score
- potential impact
- recommended action

### Security Investigation Agent

Uses callable tools to correlate information from multiple simulated security systems, including firewall logs and threat-intelligence data.

### Hypothesis Generator Agent

Generates structured threat-hunting hypotheses based on available threat intelligence and organizational context.

### Threat Hunter Agent

Investigates a hypothesis using available security data and produces a threat-hunting assessment.

### Response Decision Agent

Demonstrates a decision framework for separating:

- low-risk automated actions
- recommended actions requiring approval
- high-impact decisions requiring human escalation

### Triage & Documentation Agents

Demonstrate how specialized agents can participate in a broader incident-response pipeline.

---

## Technology

The workshop examples use:

- **Python**
- **Jupyter / Google Colab**
- **Arshai**
- **OpenRouter**
- LLM-based agents
- asynchronous Python workflows
- function / tool calling
- structured prompting

The examples currently configure:

```python
model="openai/gpt-4o-mini"
temperature=0.0
```

The model configuration can be changed depending on the provider and use case.

---

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/Mahdi-Ba/test-llm.git
cd test-llm
```

### 2. Install Arshai

```bash
pip install arshai
```

### 3. Configure an OpenRouter API key

```bash
export OPENROUTER_API_KEY="your-api-key"
```

For Google Colab, the notebooks also support loading the key from Colab Secrets.

### 4. Start with Day 1

Open:

```text
day1_single_llm_use_cases.ipynb
```

Then continue with:

```text
day2_advanced_multi_agent_systems.ipynb
```

Using the notebooks directly is recommended because some cells are designed for an interactive notebook environment.

---

## Learning Path

```text
Prompt Engineering
       ↓
Single LLM Calls
       ↓
Reusable AI Agents
       ↓
Tool Calling
       ↓
Security Investigation
       ↓
Specialized Agents
       ↓
Multi-Agent Workflows
       ↓
Human-in-the-Loop Decisions
```

This progression highlights an important engineering principle:

> Use the simplest AI architecture that can reliably solve the problem.

Not every security task requires an autonomous agent or a multi-agent system.

---

## Security & Production Considerations

These examples intentionally simplify real security infrastructure so that the architectural concepts are easier to understand.

Before adapting similar patterns for production systems, areas such as the following require additional engineering:

- authentication and authorization
- secrets management
- audit logging
- prompt-injection defenses
- structured and validated model outputs
- model evaluation
- false-positive / false-negative analysis
- observability and tracing
- retry and failure handling
- data privacy and retention
- human approval boundaries
- least-privilege access to external tools
- deterministic controls around high-impact actions

LLM output should not be treated as authoritative security evidence by itself.

---

## About the Data

The email samples, firewall logs, threat-intelligence records, alerts and user-activity examples in this repository are workshop/demo data.

They are intended to demonstrate AI-system behavior and architecture rather than represent a validated security dataset.

Similarly, ROI calculations included in the notebooks are educational examples and should not be interpreted as measured production results.

---

## Who This Repository Is For

This repository may be useful for:

- security engineers exploring LLM applications
- SOC teams evaluating AI-assisted workflows
- AI engineers learning tool calling and agent architecture
- telecom engineers exploring security automation
- instructors teaching applied AI and agentic systems
- technical leaders evaluating where LLMs can — and cannot — add value to security operations

---

## Key Takeaway

The main objective of this workshop is not simply to call an LLM.

It is to explore how AI capabilities can be introduced incrementally into an existing software and security architecture:

**single task → structured workflow → tools → specialized agents → coordinated system**

while keeping reliability, security boundaries and human oversight in mind.

---

## Repository Structure

```text
test-llm/
│
├── day1_single_llm_use_cases.ipynb
│   └── Single-LLM applications for telecom security
│
├── day1_single_llm_use_cases.py
│   └── Python export of the Day 1 notebook
│
└── day2_advanced_multi_agent_systems.ipynb
    └── Tool-enabled and multi-agent security workflows
```

---

## Author

**Mahdi Bahari**

AI & Technology Leader · Agentic AI · Software & Solution Architecture · Educator

[GitHub](https://github.com/Mahdi-Ba) ·
[LinkedIn](https://www.linkedin.com/in/mahdi-bahari-developer/)
