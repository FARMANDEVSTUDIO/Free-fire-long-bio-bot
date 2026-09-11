# 🤖 FF Bio Updater Bot

A lightweight **Telegram bot for updating Free Fire profile bios** through a dedicated API.

Built with **Python, pyTelegramBotAPI, Flask, Requests, and Gunicorn/Render deployment support**.

---

## ✨ Features

* ⚡ Fast Free Fire bio updating
* 🤖 Telegram command-based interface
* 🔑 Supports access-token based requests
* 🔗 Supports token extraction from supported URLs
* 🛡️ Optional required-channel membership verification
* 📊 Returns player information after a successful update
* 🌐 Flask health-check endpoints
* ☁️ Render deployment configuration
* 🔐 Secrets handled through environment variables
* 📝 Helpful `/start`, `/help`, and `/bio` commands

---

## 🛠️ Tech Stack

| Technology       | Purpose                    |
| ---------------- | -------------------------- |
| Python           | Core application           |
| pyTelegramBotAPI | Telegram Bot API           |
| Flask            | Web server & health checks |
| Requests         | API communication          |
| Render           | Cloud deployment           |
| GitHub           | Source control             |

---

## 📁 Project Structure

```text
ff-bio-updater-bot/
│
├── main.py
├── requirements.txt
├── render.yaml
└── README.md
```

---

## ⚙️ Requirements

* Python 3.10+
* Telegram Bot Token
* Free Fire Bio API access
* API Key
* Render account (for cloud deployment)

---

## 📦 Installation

Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/ff-bio-updater-bot.git
cd ff-bio-updater-bot
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

## 🔐 Environment Variables

Create the following environment variables:

```env
BOT_TOKEN=your_telegram_bot_token
API_KEY=your_api_key
WEBHOOK_URL=https://your-service.onrender.com
PORT=10000
```

### Environment Variable Details

| Variable      | Description                   |
| ------------- | ----------------------------- |
| `BOT_TOKEN`   | Telegram bot token            |
| `API_KEY`     | API authentication key        |
| `WEBHOOK_URL` | Public Render service URL     |
| `PORT`        | Port used by the Flask server |

> ⚠️ **Never commit your real `BOT_TOKEN` or `API_KEY` to GitHub.**

---

## 🤖 Bot Commands

### `/start`

Displays the bot welcome message and available commands.

### `/help`

Shows instructions for using the bot.

### `/bio`

Updates the Free Fire profile bio.

### Format

```text
/bio <access_token> <new bio>
```

### Example

```text
/bio your_access_token FREE FIRE PRO ⚡
```

The bot also supports extracting tokens from supported URL formats.

---

## 🌐 Web Endpoints

The Flask server provides basic endpoints for monitoring the service.

### Root

```text
GET /
```

Response:

```json
{
  "status": "running",
  "bot": "FF Bio Updater"
}
```

### Health Check

```text
GET /health
```

Response:

```json
{
  "status": "ok"
}
```

These endpoints are useful for cloud hosting platforms such as Render.

---

## ☁️ Deploy on Render

This project includes a `render.yaml` configuration.

### 1. Push the project to GitHub

```bash
git add .
git commit -m "Initial FF Bio Updater Bot"
git push
```

### 2. Create a Render Web Service

Connect your GitHub repository to Render.

Render will use:

```yaml
runtime: python
buildCommand: pip install -r requirements.txt
startCommand: python main.py
```

### 3. Add Environment Variables

Set these values in the Render dashboard:

```text
BOT_TOKEN
API_KEY
WEBHOOK_URL
```

Do **not** put private credentials directly inside the source code.

---

## 📋 Dependencies

```text
pyTelegramBotAPI==4.21.0
Flask==3.1.0
requests==2.32.3
gunicorn==23.0.0
```

---

## 🔄 How It Works

```text
User
  │
  ▼
Telegram Bot
  │
  │ /bio command
  ▼
Token Extraction
  │
  ▼
Bio Update API
  │
  ▼
API Response
  │
  ▼
Telegram Result
```

---

## 🧪 Local Development

Start the bot locally:

```bash
python main.py
```

The Flask server will run on:

```text
http://localhost:10000
```

Health check:

```text
http://localhost:10000/health
```

---

## 🔒 Security

This project uses environment variables for sensitive configuration.

Recommended:

* Never upload `.env` files
* Never commit Telegram bot tokens
* Never expose API keys
* Rotate credentials if they are accidentally leaked
* Keep production secrets inside Render Environment Variables

Example `.gitignore`:

```gitignore
.env
__pycache__/
*.pyc
.venv/
venv/
```

---

## 👨‍💻 Developer

**Farman Dev Studio**

Python • Web Development • Automation • APIs

---

## 📜 License

This project is provided for educational and development purposes.

Use the project responsibly and only with APIs/services you are authorized to access.

---

## ⭐ Support

If you find this project useful, consider giving the repository a ⭐ on GitHub.
