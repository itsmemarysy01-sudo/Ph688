PH688 TELEGRAM BOT

System Architecture & Deployment

1. System Overview

The PH688 Telegram bot is built using three main components:

1. Telegram Bot API – Handles communication between users and the bot.
2. Java Application (TelegramBots Library) – Processes messages, commands, and interactive menus.
3. Google Sheets – Stores bot content, commission information, subsidy rules, eligibility requirements, and administrator access.

The application is hosted on Vercel.

2. How the Bot Works

Step 1: User Interaction

Users open "@Ph688MarysyBot" on Telegram and send "/start".

The bot responds with an interactive menu using Telegram inline keyboards.

Step 2: Menu Navigation

Users select menu buttons to access information:

- Team Leader Promotion
- Commission Details
- Daily Subsidy
- Requirements
- How to Apply
- Contact Supervisor
- Language

The bot processes button selections through Telegram callback queries and sends the corresponding information.

Step 3: Content Retrieval

The Java application retrieves the relevant information from Google Sheets.

Google Sheets acts as the centralized content-management system, allowing authorized administrators to maintain bot information without changing the application source code.

Step 4: Language Selection

Users can select English or Taglish.

The bot displays the corresponding language version of its content.

3. Administrator Management

Authorized administrators can manage bot content through administrative commands.

Command| Function
"/update"| Update bot content
"/preview"| Preview changes
"/publish"| Publish approved changes
"/status"| View bot status
"/help"| Display administrator instructions

Administrator access is controlled through authorized Telegram user IDs.

4. Telegram Update Processing

The bot supports Telegram's two update-delivery approaches:

Webhook

- Telegram sends incoming updates to the application's HTTPS endpoint.
- Suitable for a hosted application on Vercel.
- Requires a properly configured webhook endpoint.

Long Polling

- The application continuously requests pending updates from Telegram.
- Suitable for applications designed to run a persistent polling process.

Only one update-delivery method should be active for the same bot token at a time.

5. Google Sheets Structure

The content-management spreadsheet uses the following worksheets:

Worksheet| Description
"Bot_Content"| Menu text and bilingual responses
"Commission_Rules"| Commission information
"Subsidy_Rules"| Daily subsidy policies
"Eligibility"| Team Leader requirements
"Admin_Access"| Authorized administrators
"Change_Log"| Administrative change history

6. Application Deployment

Hosting platform: Vercel
Vercel project: "telegram-serverless-bot"
GitHub repository: "Ghostv13-dev/serverless"
Production branch: "main"

Previously reported deployment details:

- Deployment status: READY
- Deployment date: November 9, 2026
- Production URL: https://telegram-serverless-bot-olive.vercel.app

The Java application is responsible for processing Telegram updates, executing bot logic, communicating with Google Sheets, and sending responses through the Telegram Bot API.

7. System Workflow

Telegram User → Telegram Bot API → Vercel Hosted Java Application → Google Sheets → Java Application → Telegram Bot API → Telegram User

8. Deployment Requirements

The application requires:

- Telegram Bot API credentials.
- A configured Vercel application.
- Google Sheets API access and authorization.
- Administrator Telegram user IDs.
- A configured webhook endpoint or long-polling process.
- Secure environment-variable management.

9. Technology Stack

Component| Technology
Bot platform| Telegram
Bot framework| TelegramBots Java Library
Application language| Java
Hosting| Vercel
Content management| Google Sheets
Source control| GitHub
User interface| Telegram Inline Keyboards
Update delivery| Webhook or Long Polling

---

PH688 Telegram Bot — System Architecture & Deployment
