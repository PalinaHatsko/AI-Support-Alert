# AI Support Alert System

## Overview

AI-powered workflow for automated support ticket analysis and mass incident detection.

The system monitors incoming support emails, extracts issue information, classifies tickets using Gemini, stores incidents in Google Sheets, and automatically notifies the team via Telegram when multiple users report the same problem.

## Architecture

```text
Gmail Trigger
      ↓
Extract Email Data
      ↓
Check Ticket Completeness
      ↓
IF / ELSE
├── Save Insufficient Ticket
└── Data Masking
        ↓
   Classify Ticket
        ↓
   Save Classified Ticket
        ↓
     Google Sheets
        ↓
 Telegram Alert (>2 similar incidents)
```

## Features

* Automatic Gmail monitoring
* AI-based issue detection
* Ticket classification with Gemini
* PII masking before processing
* Incident storage in Google Sheets
* Similar issue grouping using problem keys
* Telegram alerts for repeated incidents
* Early detection of mass support problems

## Technology Stack

* Dify Workflow
* Google Gemini
* Gmail Trigger
* Google Apps Script
* Google Sheets
* Telegram Bot API

## Example Use Case

1. A player sends a support email:

   > "I purchased a starter pack but did not receive the reward."

2. The workflow extracts and analyzes the message.

3. Gemini classifies the issue:

```json
{
  "category": "Payments",
  "severity": "High",
  "problem_key": "purchase_reward_missing"
}
```

4. The incident is saved to Google Sheets.

5. When the same issue is reported by 3 users, a Telegram alert is automatically sent to the support team.

## Repository Contents

* `Support Alert check.yml` — Dify workflow export
* Documentation (coming soon)
* Architecture diagrams (coming soon)
* Screenshots (coming soon)

## Author

Polina Gatsko

Course Project — AI in Testing & QA Automation
