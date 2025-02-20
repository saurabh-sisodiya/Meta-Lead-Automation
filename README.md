# Meta Lead Automation Script

## Overview
This Python script automates the process of fetching leads from Facebook Lead Ads and sending email notifications for new leads. The script runs every 5 minutes to check for new leads and sends an email notification with lead details.

## Features
- Automatically exchanges a short-lived token for a long-lived token.
- Fetches lead form IDs from the Facebook Graph API.
- Retrieves leads generated in the last 5 minutes.
- Parses lead data into a structured format.
- Sends an email notification for each new lead.
- Runs continuously at 5-minute intervals.

## Prerequisites
Before running this script, ensure you have the following:

- Python 3 installed
- Required Python libraries installed:
  ```bash
  pip install requests pywin32
  ```
- A Facebook App with access to Lead Ads API
- A valid **Facebook Page Access Token**
- Microsoft Outlook installed (for sending emails via Outlook)

## Setup
### 1. Update Credentials
- Replace `app_id` and `app_secret` with your Facebook App credentials.
- Replace `short_lived_token` with a valid short-lived access token.

### 2. Run the Script to Generate a Long-Lived Token
Run the script to exchange the short-lived token for a long-lived user token:
```bash
python script.py
```
Copy the long-lived token from the output and replace it in the `page_access_token` variable in the script.

### 3. Update Lead Form IDs
Replace `selected_form_ids` with the form IDs you want to fetch leads from.

### 4. Configure Email Notifications
- Update the recipient email address in the `send_email` function.
- If required, modify the email subject and body format.

## Running the Script
Run the script using:
```bash
python script.py
```
The script will:
1. Fetch lead form IDs
2. Retrieve leads from the last 5 minutes
3. Parse lead data
4. Send an email notification for each lead
5. Repeat the process every 5 minutes

## Troubleshooting
- If the script fails to fetch leads, check if the access token is still valid.
- Ensure the Facebook App has the required permissions (leads_retrieval, ads_read).
- Check if the specified lead form IDs are correct.
- Verify that Microsoft Outlook is installed and configured properly.

## Notes
- The script should be executed every **45 days** to update the **long-lived token**.
- You can automate the execution using a task scheduler (Windows Task Scheduler or a cron job).

## License
This script is for internal use only. Modify and use it at your own risk.

