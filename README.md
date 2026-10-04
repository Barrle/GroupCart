# GroupCart 🛒

This is based on the problem statement : Buy Together: Help a community combine small purchase requests into one order. Use Gemma to turn messages like “need two notebooks” into structured items, then group matching requests in code. One-day build: an editable shared order sheet with quantities and totals.

 Which is on the website : https://indore.pydata.org/hacktoberfest/


A shared supply list for classes and study groups. Add what you need, and whoever is heading to the store can buy it for you. It works from a web dashboard and from Discord.

## Features

- **Web dashboard:** live list, search, filter by person, helper leaderboard, activity feed, light and dark themes
- **Discord bot:** manage the same list with slash commands
- **Smart spelling:** typos like `notebool` are corrected using fuzzy matching and Gemini
- **Buying for others:** buyers can mark items bought for classmates, who get a notification and a Discord DM
- **Full history:** every add, buy, remove and clear is logged, with a history page and a `.txt` export

## Discord commands

| Command | What it does |
|---|---|
| `/add item quantity` | Add something to buy |
| `/remove item quantity` | Remove your item (`0` = all) |
| `/done item quantity` | Mark what you bought (`/done all` checks everything) |
| `/show` | Show what is left to buy |
| `/history` | Download the full history as a `.txt` file |
| `/help` | List the commands |

## Setup

1. **Install the requirements**
   ```bash
   pip install -r requirements.txt
   ```
2. **Add your keys.** Open `main.py` and set your Gemini API key and your Discord bot token. In the Discord Developer Portal, turn on the **Server Members Intent** for your bot. Keep both keys private and never upload them to GitHub.
3. **Start the server** (terminal 1)
   ```bash
   uvicorn server:app --port 8000
   ```
4. **Start the bot** (terminal 2)
   ```bash
   python main.py
   ```
5. Open <http://localhost:8000> to use the dashboard.

## Project files

```
server.py      FastAPI backend and SQLite database (data.db is created on first run)
main.py        Discord bot
index.html     Dashboard
history.html   History page
```
