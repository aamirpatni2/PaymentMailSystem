Invoice Notification Automation – n8n Workflow
Overview

This project automates customer email notifications using n8n, integrating Google Sheets and Gmail.
The workflow reads data from a Google Sheet, filters rows based on conditions (such as pending or paid invoices), and automatically sends personalized email notifications to customers.

Workflow Structure
Nodes Explanation

When Clicking 'Execute Workflow'

Manual trigger used to start the workflow during testing or debugging.

Get Row(s) in Sheet

Reads customer and invoice data from a connected Google Sheet.

Columns include:

Customer ID

Customer Name

Customer Email

Customer Phone

Invoice Due Date

Payment Status

Filter

Filters rows according to specific rules (e.g., upcoming due invoices or overdue payments).

Ensures that only relevant rows proceed to the next step.

Switch (Mode: Rules)

Splits filtered data into branches based on invoice status:

Branch 1: For unpaid or overdue invoices → Sends reminder email.

Branch 2: For paid invoices → Sends thank-you email.

Send a Message (Gmail Node)

Sends custom email templates to customers with pending invoices.

Send a Message1 (Gmail Node)

Sends confirmation or appreciation emails to customers with paid invoices.

Key Features

Automated Email Delivery: Personalized emails sent directly through Gmail.

Google Sheet Integration: Dynamic data source that updates automatically.

Conditional Logic: Intelligent branching using the Switch node for different invoice states.

Scalable Workflow: Easily adaptable for CRM systems, payment reminders, or marketing automation.

Manual or Scheduled Execution: Can be triggered manually or through a CRON schedule for periodic checks.

Use Case

This workflow is ideal for:

Small businesses managing invoices and client communication.

Freelancers automating client reminders.

Teams needing a simple no-code automation solution integrated with Google Workspace.

Setup Instructions

Clone this repository:

git clone https://github.com/yourusername/invoice-notification-n8n.git
cd invoice-notification-n8n


Open n8n (locally or via cloud).

Import the workflow file (workflow.json) into n8n.

Connect the following credentials:

Google Sheets API for reading invoice data.

Gmail API for sending emails.

Configure your sheet columns to match the workflow fields:

Customer ID | Customer Name | Customer Email | Customer Phone | Invoice Due | Payment Status


Adjust the filter and switch rules according to your invoice logic.

Test the workflow using Execute Workflow.

Optionally, set up a Schedule Trigger to automate daily execution.

Example Output
Customer ID	Customer Name	Customer Email	Invoice Due	Payment Status
CUST001	Richard Gross	baileytamara@gmail.com
	2025-01-23	Pending
CUST004	Dawn Gomez	kellycarr@gilbert-diaz.com
	2025-01-25	Paid
Future Enhancements

Add payment gateway integration for real-time status updates.

Include Slack or WhatsApp notifications.

Log email status in a Google Sheet for auditing.

License

This project is open source and available under the MIT License.
