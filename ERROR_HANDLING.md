#  Used Gadgets Marketplace Bot - PawnSafe - Error Handling
## Table of Contents
1. [Database Errors](#database-errors)
2. [API Errors](#api-errors)
3. [Polling Errors](#polling-errors)
4. [General Error Handling](#general-error-handling)
5. [Troubleshooting](#troubleshooting)

---

### 1. Database Errors

- **Description**: Errors related to database operations (e.g., reading, writing).
- **Common Causes**:
  - Corrupted database file
  - Incorrect database path
  - SQL syntax errors
- **Handling Strategy**:
  - All database calls use error-handling callbacks to capture issues.
  - Error details are logged to the console for developer reference.
  - Users are sent a friendly error message, such as:
    ```javascript
    db.get(`SELECT * FROM products`, (err, row) => {
      if (err) {
        console.error('Error fetching product:', err);
        bot.sendMessage(chatId, 'Error: Unable to fetch product.');
      }
    });
    ```

---

### 2. API Errors

- **Description**: Issues connecting with the Telegram API (e.g., network timeouts, invalid responses).
- **Common Causes**:
  - Network issues
  - Invalid API token
  - Exceeding Telegram rate limits
- **Handling Strategy**:
  - The bot logs API errors to the console for analysis.
  - A single instance of the bot should run to prevent `409 Conflict` errors.
  - Retry connection or prompt the user to try again if possible.

---

### 3. Polling Errors

- **Description**: Errors that occur during message polling, which allows the bot to listen for updates.
- **Common Causes**:
  - Multiple instances of the bot running simultaneously
  - Network interruptions
- **Handling Strategy**:
  - Common polling errors (e.g., `EFATAL` or `ENOTFOUND`) are logged, with clear indicators of network or instance issues.
  - Suggested fix: Ensure only one bot instance is active to avoid conflicts.

---

### 4. General Error Handling

- **Error Logging**:
  - Use `console.error()` to log error details during development.
  - Minimize logging to console in production, using logging libraries if needed.
  
- **User Messaging**:
  - All user-facing error messages are friendly and avoid technical jargon.
  - Examples:
    ```javascript
    bot.sendMessage(chatId, 'Oops! Something went wrong. Please try again later.');
    ```

- **File Naming**:
  - File names and error logs should be clear and self-explanatory.

---

### 5. Troubleshooting

For persistent issues:
1. Check if the database file path in `.env` is correct.
2. Confirm that only one instance of the bot is running.
3. Ensure network stability, especially for Telegram API access.

If the issue persists, refer to the full error log for specific troubleshooting.
