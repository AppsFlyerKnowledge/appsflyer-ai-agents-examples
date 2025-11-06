# Executive Summary n8n Flow Setup Guide

This guide walks you through the process of importing and configuring AppsFlyer Executive Summary n8n flow from GitHub.

## Overview

The Executive Summary Agent generates comprehensive performance dashboards for your app by retrieving data from AppsFlyer via MCP. The AI agent automatically fetches key performance metrics including clicks, installs, and D1/D7/D14 cohort data (installs, revenue, ROI), then creates a beautifully formatted HTML dashboard that is emailed to your team.

## Prerequisites

- An n8n account and workspace access
- AppsFlyer MCP token
- OpenAI API key
- Gmail account for sending alerts
- GitHub repository URL containing the n8n flow [JSON file](https://raw.githubusercontent.com/AppsFlyerKnowledge/appsflyer-ai-agents-examples/refs/heads/main/n8n/executive_summary/executive_summary_agent_gmail.json)

## Import Flow from GitHub

### Step 1: Create or Access Your n8n Workspace

Before importing the flow, ensure you have a workspace set up in n8n.

![Create workspace](images/n8n_create_workspace.png)

### Step 2: Import the Flow from GitHub URL

1. In your n8n dashboard, click on the **Import** option (usually found in the top menu or sidebar).

2. Select **Import from URL** to import the flow directly from your GitHub repository.

![Import URL point](images/n8n_import_url_point.png)

3. Click on the URL input field to enter your GitHub raw file URL.

![Import URL dialog](images/n8n_import_url_dialog.png)

4. Paste your GitHub raw file URL: `https://raw.githubusercontent.com/AppsFlyerKnowledge/appsflyer-ai-agents-examples/refs/heads/main/n8n/executive_summary/executive_summary_agent_gmail.json` and click **Import**.

### Step 3: Configure Flow Fields

After importing the flow, you'll need to configure various fields and credentials.

1. Double-click the **Edit Fields** node.

![Click edit fields](images/n8n_click_edit_fields.png)

2. Update the necessary fields with your specific values and configurations.

![Update fields](images/n8n_update_fields.png)

### Step 4: Configure Credentials

The flow requires several credentials to function properly. Set up each one as follows:

#### OpenAI Credentials

1. Navigate to the OpenAI node in your flow and configure the credentials.

![Dashboard click OpenAI](images/n8n_dashboard_click_openai.png)

2. Click to create a new OpenAI token.

![OpenAI new token point](images/n8n_openai_new_token_point.png)

3. Enter your OpenAI API key in the dialog.

![OpenAI new token dialog](images/n8n_openai_new_token_dialog.png)

#### Gmail Credentials

1. Navigate to the Gmail node in your flow and configure the credentials.

![Dashboard click Gmail](images/n8n_dashboard_click_gmail.png)

2. Click to create a new Gmail token.

![Gmail token point](images/n8n_gmail_token_point.png)

3. Enter your Gmail credentials in the dialog.

![Gmail token dialog](images/n8n_gmail_token_dialog.png)

#### MCP (Model Context Protocol) Credentials

1. Navigate to the MCP Client node in your flow and configure the credentials.

![Dashboard click MCP](images/n8n_dashboard_click_mcp.png)

2. Click to create a new MCP token.

![MCP dialog](images/n8n_mcp_dialog.png)

3. Enter your MCP token in the dialog.

![MCP new token dialog](images/n8n_mcp_new_token_dialog.png)

## How It Works

1. **Data Retrieval**: The AI agent uses AppsFlyer MCP to fetch performance data for the specified app and date range. It retrieves metrics including:
   - Clicks and installs
   - D1, D7, and D14 cohort performance (installs, revenue, ROI)
   - Key performance indicators

2. **Dashboard Generation**: The agent generates a complete HTML dashboard with:
   - Executive Summary section
   - Key Performance metrics
   - Actionable recommendations
   - Visual tables with performance data
   - Blue and green themed styling with emojis for visual appeal

3. **File Conversion**: The generated HTML dashboard is converted to a file with a timestamped filename for easy tracking.

4. **Email Delivery**: The formatted HTML dashboard is sent as an attachment to the configured email addresses, with a professional email template that includes:
   - Summary of what's inside the dashboard
   - App information
   - Generation timestamp

## Next Steps

After completing the setup:

1. Save your flow
2. Test the workflow by running it manually
3. Activate the workflow if you want it to run automatically

## Troubleshooting

- Ensure all credentials are properly configured
- Verify that your GitHub URL points to the correct raw file
- Check that all required nodes have valid connections
- Review n8n logs for any error messages

---

**Author:** Liaz Kamper
