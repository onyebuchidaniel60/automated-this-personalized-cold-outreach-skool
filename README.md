# AI-Powered Skool Cold Outreach Automation

This workflow provides an end-to-end solution for automated, highly personalized cold outreach targeting Skool community members. It leverages AI to research leads and draft context-aware emails, ensuring high engagement for coaching businesses.

## 🚀 Features

- **Skool Scraping:** Uses the **Apify Skool Email Scraper** to extract targeted leads based on specific community keywords.
- **Automated Research:** Integrates **Tavily Search** to find recent information and activity regarding each lead to provide context for personalization.
- **AI Copywriting:** Employs **GPT-4o (via OpenRouter)** to draft casual, 5-line personalized emails that address specific lead interests and fitness goals.
- **Email Rotation:** Automatically switches between three different Gmail accounts (`decloglabs@gmail.com`, `Lucas.premat@gmail.com`, and `vault2451@gmail.com`) to manage daily sending limits and maintain deliverability.
- **CRM Integration:** Automatically logs all lead data, including the AI-generated email subject and body, into a **Google Sheet** ("Outreach data skool Jay").
- **Human-like Timing:** Features a 150-second **Wait node** between emails to avoid spam filters and mimic manual outreach.

## 🛠️ Prerequisites

To use this workflow, you will need:
- An **n8n** instance.
- **Apify API Key** (for Skool scraping).
- **Tavily API Key** (for lead research).
- **OpenRouter API Key** (for GPT-4o access).
- **Google Sheets OAuth2** credentials.
- **Gmail OAuth2** credentials for three separate sending accounts.

## ⚙️ How It Works

1.  **Trigger:** The workflow is initiated via a **Webhook** receiving `skoolKeywords`.
2.  **Scrape:** Apify finds leads in Skool communities matching the provided keywords.
3.  **Research:** For every lead, the workflow performs a Tavily search to find recent relevant data about the individual.
4.  **AI Drafting:** The AI agent follows a strict template to write a friendly, non-pushy email, including a call-to-action to a Calendly booking link.
5.  **Smart Rotation:** The **Switch node** selects one of the three configured Gmail accounts to send the email.
6.  **Tracking:** All lead details and the sent message status are recorded in Google Sheets.

## 📦 Installation

1. Download the `automated cold outreach skool.json` file.
2. Import the JSON file into your n8n instance.
3. Configure your API credentials for:
   - Apify
   - Tavily
   - OpenRouter
   - Google Sheets
   - Gmail (3 accounts)
4. Update the **Google Sheet ID** and the **Calendly link** in the "Write email" node to match your own business details.
