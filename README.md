#  Used Gadgets Marketplace Bot - PawnSafe

A Telegram bot to create a trusted marketplace for SDU students to buy and sell used gadgets. 

---

## Table of Contents
1. [How to Install](#how-to-install)
2. [How to Run](#how-to-run)
3. [Logic Flow](#logic-flow)
4. [Entry Point](#entry-point)
5. [Environment Variables](#environment-variables)
6. [Additional Documentation](#additional-documentation)

---

### 1. How to Install

1. Clone the repository:
    ```bash
    git clone <repository-url>
    cd <project-directory>
    ```

2. Install dependencies:
    ```bash
    npm install
    ```

### 2. How to Run

To start the bot, ensure your `.env` file is set up with the correct credentials:

- **Run the bot**:
    ```bash
    node src/bot.js
    ```

- **Run with Nodemon** (for automatic restart on code changes):
    ```bash
    npm install -g nodemon
    nodemon src/bot.js
    ```

### 3. Logic Flow

The bot’s logic includes:
   - **Start Point**: `src/bot.js` is the entry point, initializing the bot and configuring listeners for commands and callbacks.
   - **Callback Handling**: Manages responses to user interactions.
   - **Product Catalog**: Fetches and displays products with navigation buttons.
   - **Error Handling**: Errors are logged, and user-friendly messages are sent.

### 4. Entry Point

The main entry point is `src/bot.js`, which:
1. Loads environment variables.
2. Initializes the bot instance.
3. Registers command handlers and imports callback handlers from `src/handlers/callback.js`.
4. Starts polling for messages and updates.

### 5. Environment Variables

Use a `.env` file for configuration:
```plaintext
TELEGRAM_TOKEN=your-telegram-bot-token
DATABASE_URL=./data/database.sqlite

Load variables with dotenv:

require('dotenv').config();
const token = process.env.TELEGRAM_TOKEN;

---
6. Additional Documentation
For more details:

Error Handling and Troubleshooting
Code conventions
Product documentation
Software architecture schemas
Database Schema
Sequence diagram
Technical decision log

## Documentation Links

- [ERROR_HANDLING.md](docs/ERROR_HANDLING.md)
- [CODE_CONVENTIONS.md](docs/CODE_CONVENTIONS.md)
- [PRODUCT_DOCUMENTATION.md](docs/PRODUCT_DOCUMENTATION.md)
- [SOFTWARE_ARCHITECTURE_SCHEMAS.md](docs/SOFTWARE_ARCHITECTURE_SCHEMAS.md)
- [DATABASE_SCHEMA.md](docs/DATABASE_SCHEMA.md)
- [SEQUENCE_DIAGRAM.md](docs/SEQUENCE_DIAGRAM.md)
- [TECHNICAL_DECISION.md](docs/TECHNICAL_DECISION.md)


