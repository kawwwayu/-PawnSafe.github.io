# Technical Decision Log

### Project:  Used Gadgets Marketplace Bot - PawnSafe

---

## 1. Overview

This document outlines the major technical decisions and the rationale behind each, covering the chosen technologies, design patterns, and architectural decisions for developing the PawnSafe bot.

---

### 2. Decisions and Rationales

| **Decision**                  | **Description**                                                                                  | **Alternatives Considered**                          | **Rationale**                                                                                         |
|-------------------------------|--------------------------------------------------------------------------------------------------|------------------------------------------------------|--------------------------------------------------------------------------------------------------------|
| **Language and Framework**    | Use **JavaScript** with **Node.js** for backend development.                                     | Python with Telebot API                              | Node.js allows for faster, real-time processing and integrates well with the Telegram API.             |
| **Database**                  | Use **SQLite3** as a lightweight, file-based database for early-stage development.               | PostgreSQL, MySQL                                    | SQLite3 provides simplicity, no setup time, and is sufficient for initial local data storage.          |
| **Bot API Integration**       | Integrate with **Telegram API** for handling user interactions.                                  | Custom messaging API                                 | Telegram API offers built-in support for bot functions and handles interaction complexities.           |
| **Environment Variables**     | Use **dotenv** to manage environment variables and sensitive data (e.g., tokens).               | Direct variable storage in code                      | dotenv ensures security and flexibility, especially for API keys and DB configurations.                |
| **Bot Hosting**               | Host on a **cloud server** with a low-latency region close to users for performance.            | Local server, dedicated hosting                      | Cloud hosting is scalable, offers better uptime, and can adjust to increased user activity.            |
| **Architecture Style**        | Modularize code into distinct folders for `handlers`, `services`, `utils`, and `db`.            | Single main file structure                           | Modularization supports maintainability and debugging in complex bot flows.                            |
| **Error Handling Strategy**   | Implement centralized error logging and user-friendly messages for database and API errors.     | Ignore non-critical errors                           | Central error handling increases reliability and user experience by mitigating potential issues.       |
| **Bot Command Processing**    | Use **command-handler.js** and **callback-handler.js** to manage commands and responses.         | Single handler file                                  | Separating logic enhances code readability and makes debugging and future scaling easier.              |
| **Authentication Approach**   | Authenticate users through Telegram's bot system (no external signup required).                 | Separate login system                                | Telegram's authentication maintains simplicity and minimizes friction for student users.               |
| **Product Evaluation Logic**  | Implement predefined categories (“Like New,””Excellent,” “Good,””Well used,”“Fixed”) for product quality.          | Full custom rating scale                             | Categories are quick and align with students’ needs for fast decision-making in purchases.             |

---

### 3. Future Considerations

- **Database Scaling**: As the user base grows, consider upgrading to a full-fledged SQL solution (PostgreSQL or MySQL) for optimized queries.
- **Advanced Error Monitoring**: Evaluate the implementation of tools like Sentry for enhanced error tracking.
- **Additional Bot Features**: Potential to add user rating and review functionalities based on post-release feedback.
  
### 4. Review

- Document to be reviewed and updated periodically as project needs evolve.

---


