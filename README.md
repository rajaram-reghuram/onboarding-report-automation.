<a name="readme-top"></a>

<!-- PROJECT LOGO -->
<div align="center">
  <h3 align="center">Automated SaaS Onboarding Triage Pipeline</h3>

  <p align="center">
    Autonomous AI-driven triage architecture for enterprise SaaS onboarding.
    <br />
    <a href="https://app.notion.com/p/Automated-SaaS-Onboarding-Triage-Pipeline-38d5f0f83a3d802ba246c547326c241b?source=copy_link"><strong>Explore the docs »</strong></a>
    <br />
  </p>
</div>

<!-- ABOUT THE PROJECT -->
## About The Project

This repository contains the architecture and implementation for an automated triage system that replaces manual JSON payload validation with deterministic pipeline orchestration.

**Key Features:**
* **Event-Driven Ingestion:** Webhook-based capture of enterprise configuration payloads.
* **Agentic Validation:** Gemini 2.5 Flash analysis utilizing deterministic prompt engineering for block-list identification.
* **Automated PDF Generation:** Serialization of markdown into enterprise-grade PDF artifacts via external microservices.
* **Dynamic Metadata Handling:** Custom JavaScript injection for enterprise-grade filename management.

---

## Technical Architecture

The pipeline is orchestrated via n8n to ensure deterministic, scalable execution:

* **Webhook Trigger**: Ingests `POST` payloads containing account metadata, ingestion settings, and pipeline status arrays.
* **Gemini 2.5 Flash Agent**: Analyzes the payload with a temperature of 0.1 for high-fidelity reasoning, identifying configuration blockers without conversational filler.
* **State Management**: Aggregates client data with triage timestamps to maintain an immutable audit object and perfect data lineage.
* **Binary Extraction**: Finalizes each runbook with a unique filename via JavaScript injection, mapping files directly to the `company_name` attribute in the payload.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- GETTING STARTED -->
## Getting Started

To deploy this workflow locally or in your n8n instance:

### Installation

1. Clone the repo
   ```sh
   git clone [https://github.com/your_username/saas-onboarding-automation.git](https://github.com/your_username/saas-onboarding-automation.git)
