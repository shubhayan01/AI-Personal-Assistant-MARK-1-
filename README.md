📊 MARK 1 v9 – Smart Business Automation Workflow (n8n)

MARK 1 v9 is a conversational automation system built on **n8n** that transforms simple text instructions into intelligent business actions. From adding clients to generating invoices, creating calendar events, managing timelines, and sending reminders — everything runs through a unified workflow triggered via natural language.

 🧠 Key Capabilities

- 🗣 **Natural Language Parsing**  
  Interprets plain-text instructions like "add a new client, John, john@email.com, ..." into structured data.

- 🗂 **Business Operation Automation**  
  Supports:
  - Adding clients
  - Generating invoices
  - Creating Google Calendar events
  - Logging customer interactions
  - Sending reminders via Telegram
  - Assigning projects and tasks

- 🧾 **Google Sheets Integration**  
  Dynamically appends structured data into designated sheets:  
  - Clients  
  - Projects  
  - Revenue  
  - Reminders  
  - Timeline  
  - Tasks

- 📅 **Google Calendar Sync**  
  Automatically schedules meetings/reminders extracted from text input.

- 📬 **Telegram Notifications**  
  Sends:
  - 1-day and 1-hour prior event alerts
  - Data reports in CSV format  
  - Personalized client messages

## ⚙️ Workflow Design (n8n)

- 🟦 **Switch Nodes** – Detect intent from message (e.g., “add client”, “wish client”)
- 💻 **Code Nodes** – Parse user input, extract entities like name, email, etc.
- 🧾 **Google Sheets Nodes** – Store parsed data into appropriate spreadsheets
- 📅 **Google Calendar Node** – Create and schedule events
- 📩 **Telegram Nodes** – Send reminders or documents via bot
- ⏱ **Wait Nodes** – Manage time-based reminders

## 📁 Structure Overview

Mark_1_v9/
├── Switch (Intent detection)
├── Code Nodes (NLP/Parsing)
├── Google Sheets (Data storage)
├── Google Calendar (Event sync)
├── Telegram Bots (Alerts/Reports)
├── Wait Nodes (Scheduled notifications)
└── Dynamic Workflow Routing (Based on message content)

markdown
Copy
Edit

## 🔐 Credentials Used

- **Google Sheets OAuth2**
- **Google Calendar OAuth2**
- **Telegram Bot Token**

> All credentials are abstracted via environment bindings and managed securely in the n8n cloud/local instance.

## 🧪 Sample Inputs

Add a new client, Rohan, rohan@email.com, 9876543210, Andheri Office

Make invoice, Rohan, ₹3000, SEO Service, Paid, 31 July 2025

Add reminder, Project deadline, 2 August 2025, 3:00PM, Push GitHub changes

Wish client, Rohan, rohan@email.com, Birthday, 3 August 2025

pgsql
Copy
Edit

## 🛠 How to Run

1. Import the `Mark_1_v9 n8n backup.json` into your [n8n](https://n8n.io) instance
2. Connect your Google Sheets, Google Calendar, and Telegram integrations
3. Set up a webhook or trigger mechanism (Telegram/HTTP) to receive messages
4. Start sending commands in natural language!

## 📌 Notes for Reviewers

- All parsing is done with robust error handling in JS Code nodes
- Workflow supports failover for missing/incorrect fields
- Ready to be scaled per client with isolated workflow logic

---

> **Created by:** [Shubhayan Banerjee](https://github.com/shubhayan01)  
> **Interview Note:** This project demonstrates deep integration of automation, nat
