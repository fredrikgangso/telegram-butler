# Telegram Butler — Too Bee

A lightweight Telegram "butler" bot (Too Bee) that automates common chat tasks, responds to commands, and integrates with external services. Designed to be simple, extensible, and easy to run locally or in Docker.

## Features

- Handle commands and natural replies
- Per-chat configuration (prefixes, permissions)
- Scheduled tasks and reminders
- Plug-in friendly: add handlers for new services
- Minimal dependencies, focused on reliability

## Quick start

Prerequisites

- Telegram bot token (via BotFather)
- Node 16+ or Python 3.9+ (project language decided in code)
- Git and Docker (optional)

Clone and install

```bash
git clone <repo-url>
cd telegram-butler-too-bee
# install dependencies (example for Node)
npm install
```

Configure

- Create a .env file (or use Docker secrets)

```
TELEGRAM_TOKEN=your_bot_token_here
BOT_ENV=production
ADMIN_USER_IDS=12345678,87654321
```

Run

```bash
# local
npm start

# or with Docker
docker build -t tb-too-bee .
docker run --env-file .env tb-too-bee
```

## Usage

Common commands

- /help — show available commands
- /status — bot health and uptime
- /remind 10m Take a break — schedule a reminder
- /config set prefix ! — set command prefix for this chat
- /plugins list — list installed plugins

Examples

- Private chat: use slash commands for direct tasks
- Group chat: mention the bot or use a configured prefix

## Configuration & Extensibility

- Handlers live under `src/handlers` (or `handlers/`)
- Add a new handler by implementing an interface (see `examples/`)
- Environment-driven config for tokens, webhooks, polling mode
- Support for middleware (logging, auth, rate-limiting)

## Development

- Run tests: `npm test`
- Lint: `npm run lint`
- Start dev server: `npm run dev` (auto-reload)

Structure (example)

```
/
├─ src/
│  ├─ bot.js
│  ├─ handlers/
│  └─ services/
├─ config/
├─ docs/
└─ Dockerfile
```

## Contributing

- Open issues for bugs or feature requests
- Fork, create a branch `feat/my-feature`, and submit a PR
- Follow code style and include tests for new functionality

## Troubleshooting

- Check bot token and network connectivity
- Increase logging level to DEBUG in .env for diagnostics
- Verify webhook URL if using webhooks

## License

MIT — see LICENSE file

## Support

Open an issue or contact the maintainers listed in the repository.
