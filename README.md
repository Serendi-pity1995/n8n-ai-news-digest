# AI News Digest Workflow for n8n

This n8n workflow automates the process of gathering daily AI news, summarizing it using an LLM, and sending a beautifully formatted email digest.

## Features
- **Data Source**: Tavily API (Search & Extract News).
- **Processing**: JavaScript cleaning to remove noise from web scraping.
- **AI Summary**: Google Gemini (or any LLM) to summarize articles into a concise "Daily Selection".
- **Delivery**: Gmail (HTML formatted email with a clean, literary style).

## Prerequisites
To use this workflow, you need:
1.  **n8n**: Self-hosted or Cloud version.
2.  **Tavily API Key**: For searching news.
3.  **Google Gemini API Key**: For generating summaries.
4.  **Gmail Credentials**: OAuth2 credentials to send emails.

## How to use
1.  Download the `n8n_news_digest_workflow.json` file from this repository.
2.  Open your n8n dashboard.
3.  Click **Import workflow** (top right) -> **From File**.
4.  Configure your credentials in the `Tavily`, `Google Gemini`, and `Gmail` nodes.
5.  In the Tavily node, enter the topic you’re interested in under the ‘query’ field.
6.  Update the **Email Digest to Subscriber** node:
    - Change `To Email` to your recipient address.
    - Change `CC Email` (optional).
7.  Activate the workflow!

