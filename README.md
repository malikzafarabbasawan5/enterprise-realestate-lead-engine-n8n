# Enterprise Real Estate VIP Lead Qualification & Routing Engine

An autonomous, production-grade inbound lead qualification and routing engine built with **n8n** and **Google Gemini 1.5 Flash**.

## Overview
High-ticket real estate sales require rapid speed-to-lead. This system automates the intake, normalization, AI-powered intent scoring, and conditional routing of property inquiries, ensuring high-net-worth investors receive immediate attention while standard leads are automatically nurtured.

## Architecture & Data Flow

1. **Ingestion (Webhook):** Captures incoming real-time lead submissions from web portals and landing pages.
2. **Deterministic Normalization (Code Node):** Cleans irregular numerical budget strings (handling variations like "Crore", "Lakh", "M") into standard integers.
3. **Cognitive Evaluation Layer (Gemini 1.5 Flash):** Evaluates buyer intent, purchasing timeline, and investment magnitude to produce an intent score (1–100) and strategic pitch angle.
4. **Deterministic Decision Gate (If Node):** Evaluates VIP eligibility based on budget threshold (>= 15,000,000 PKR) and intent score.
5. **Multi-Channel Dispatch:**
   - **VIP Pathway:** Automatically sends an off-market luxury portfolio to the buyer and triggers an urgent priority dispatch to the Sales Director.
   - **Standard Pathway:** Sends an automated acknowledgment email.
   - **Audit Persistence:** Persists qualification metadata and timestamps directly to Google Sheets.

## Tech Stack
- **Orchestration:** n8n
- **Cognitive Engine:** Google Gemini 1.5 Flash
- **Data Persistence:** Google Sheets
- **Communication Layer:** Gmail API
- **Execution Runtime:** Node.js (JavaScript Code Nodes)

## How to Import
1. Download the exported workflow file from this repository.
2. Open your n8n instance.
3. Click **Workflows** > **Import from File** and select the JSON file.
4. Configure your credentials for **Google Gemini**, **Gmail**, and **Google Sheets**.
5. Activate the workflow.
