HackerNews-keyword-tracker

A Node-RED flow that automatically fetches Hacker News stories, filters them by keywords, ranks hotness by score & comments, and delivers a daily Top 20 digest per keyword via e-mail.

✨ Features

Keyword-based story filtering (supports multiple keywords)

Hotness score (weighted by upvotes & comments)

Top 20 stories per keyword, aggregated into a single daily e-mail

Dashboard front-end: keyword input & live story table

Works with official Hacker News API

Optional: local caching to bypass API’s 500-item limit

📂 Project Structure
flows/hn-digest.flow.json   # Exported Node-RED flow
screenshots/                # Effect screenshots
.env.example                # Example environment configuration
README.md
LICENSE

🔧 Requirements

Node.js LTS & Node-RED ≥ 3.x

Node-RED Palettes:

node-red-dashboard

node-red-node-email

node-red-node-ui-table (optional)

🚀 Quick Start

Install Node-RED:

npm install -g --unsafe-perm node-red
node-red


Open http://localhost:1880 and import flows/hn-digest.flow.json.

Install required palettes in “Manage Palette”.

Configure the e-mail node:

SMTP server (e.g. smtp.gmail.com)

Port (465/587)

Username (your email address)

Password (app-specific password, not your login password)

Recipient address

Deploy.

At 09:30 AM on weekdays, the system sends the digest automatically.

You can also trigger manually from the dashboard.

⚙️ Configuration

Keywords: set in dashboard UI or .env → KEYWORDS=AI,IoT,UNS,iOS.

E-mail: use .env variables for SMTP_USER / SMTP_PASS, or configure directly in the e-mail node.

Time window: by default, only stories in the last 24 hours are included.

Hotness weight: editable in the function node (default: score*0.5 + comments*0.5).

📸 Screenshots

Dashboard UI


Daily E-mail Digest


Node-RED Flow Overview


📝 License

MIT License. Feel free to fork, modify and share.
