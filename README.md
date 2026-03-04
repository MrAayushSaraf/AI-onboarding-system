🧠 AI Onboarding Automation System
Offline-First • Versioned • Reproducible • Zero-Cost Architecture
📌 Overview

This project simulates a production-grade onboarding automation pipeline that converts onboarding conversations into structured, version-controlled AI voice agent configurations.

The system transforms transcripts or audio recordings into structured JSON rules representing:

Business hours

After-hours routing

Emergency handling

CRM / integration setup

Missing configuration detection

The architecture is designed to resemble a small internal automation product rather than a simple script.

🎯 Problem Statement

During AI voice agent onboarding, configuration details are typically collected through live conversations.

These conversations must be converted into structured rules that define system behavior.

Manual extraction is:

Time-consuming

Inconsistent

Error-prone

Hard to audit

This system automates the transformation while maintaining configuration version history.

🏗 Architecture
Audio (.mp3 / .wav)
        ↓
Whisper (Local Speech-to-Text)
        ↓
Ollama (Local LLM - Mistral)
        ↓
Structured JSON Extraction
        ↓
Versioned Configuration Storage
        ↓
Streamlit Dashboard Visualization
Design Principles

Fully offline-first

No paid API dependencies

Strict JSON schema output

Version-controlled configurations

Missing-field detection

Minimal manual intervention

🧩 Tech Stack
Layer	Technology	Purpose
Speech-to-Text	Whisper (local)	Audio → Transcript
LLM Extraction	Ollama (Mistral)	Structured rule extraction
Processing	Python	Rule building & validation
Storage	JSON (versioned)	Config persistence
Dashboard	Streamlit	Config inspection
Containerization	Docker	Reproducibility
📂 Repository Structure
ai-onboarding-automation/
│
├── README.md
├── requirements.txt
├── docker-compose.yml
│
├── backend/
│   ├── main.py
│   ├── llm/
│   ├── stt/
│   ├── processors/
│   ├── versioning/
│   └── data/
│       ├── raw/
│       ├── transcripts/
│       └── configs/
│
└── dashboard/
    └── dashboard.py
🔄 Versioning Model

The system supports configuration evolution:

demo_v1 → Generated from initial demo conversation

onboarding_v2 → Updated configuration after onboarding

Each configuration:

Is saved as a timestamped JSON file

Can be inspected via dashboard

Enables auditability

Preserves change traceability

Sample configurations are included in:

backend/data/configs/
📊 Dashboard Features

The Streamlit dashboard allows:

Viewing generated configurations

Inspecting structured JSON

Counting extracted fields

Detecting missing information

Verifying emergency handling logic

This enables evaluation without running the full pipeline.

🔐 Ethics & Data Handling

This repository follows strict data responsibility practices:

No customer data beyond provided samples

No recordings published publicly

No external APIs used

No personal information added

All processing occurs locally

🚀 Running Locally (Optional)

Note: Sample transcripts and generated configuration files are included.
The project can be evaluated without running the full pipeline.

1️⃣ Install Ollama
ollama pull mistral

Start Ollama:

ollama run mistral
2️⃣ Run Dashboard
docker-compose up

Open:

http://localhost:8501
📦 Sample Data Included

The repository contains:

Sample transcript file

Sample demo_v1 configuration

Sample onboarding_v2 configuration

This ensures the system is reviewable without additional setup.

🏆 What Makes This “Great”

Product-style architecture

Fully offline execution

Zero-cost dependency model

Version-controlled outputs

Schema-driven extraction

Change traceability

Reproducible environment

Clear separation of concerns

This project demonstrates structured thinking and practical automation design.

📌 Submission Notes

No API keys required

No paid services required

Sample outputs included

Docker included for reproducibility

Repository structured for evaluator clarity

📈 Future Improvements

Automated configuration diff visualization

Formal JSON schema validation

Extraction confidence scoring

Unit test coverage

UI-based version comparison
