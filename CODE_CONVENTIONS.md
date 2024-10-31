#  Used Gadgets Marketplace Bot - PawnSafe - Code Conventions
---

## Table of Contents
1. [JavaScript Style](#javascript-style)
2. [File Naming](#file-naming)
3. [Comments](#comments)
4. [Error Logging](#error-logging)
5. [Modularization](#modularization)

---

### 1. JavaScript Style

- **Code Formatting**: Follow JavaScript Standard Style.
  - Use **2 spaces** for indentation.
  - Always use **semicolons** at the end of statements.
  - Use **camelCase** for variable and function names.
  
- **Example**:
    ```javascript
    function fetchProduct(productId) {
      const product = db.getProductById(productId);
      console.log('Fetched product:', product);
      return product;
    }
    ```

---

### 2. File Naming

- **Convention**: Use lowercase letters and hyphens for file names, separating words with dashes.
  - **Example**: `callback-handler.js`, `product-catalog.js`.
- **Organize by Functionality**: Group files by their functionality (e.g., separate handlers, utilities).

---

### 3. Comments

- **Section Headers**: Use comments to mark major sections in the code.
- **Function Descriptions**: Add a brief comment explaining each function's purpose.
- **Database Queries**: Clearly annotate all database interactions.

- **Example**:
    ```javascript
    // Retrieve product from database by ID
    function getProduct(id) {
      // Fetch product data from 'products' table
      db.get(`SELECT * FROM products WHERE id = ?`, [id], (err, row) => {
        if (err) {
          console.error('Database error:', err);
          return null;
        }
        return row;
      });
    }
    ```

---

### 4. Error Logging

- **Console Errors**: Use `console.error()` for logging errors, especially during development.
- **Avoid Production Logging**: Minimize console logging in production; use a logging library if needed.
- **User-Friendly Messages**: Ensure errors logged to users are clear and non-technical.

- **Example**:
    ```javascript
    db.get(`SELECT * FROM products`, (err, row) => {
      if (err) {
        console.error('Error fetching product:', err);
        bot.sendMessage(chatId, 'Error: Unable to fetch product.');
      }
    });
    ```

---

### 5. Modularization

- **Separate by Functionality**: Use modules to separate concerns (e.g., handlers for different bot commands).
- **Reuse Code**: Organize reusable code into utility functions.
- **Example**:
  ```javascript
  // Inside src/utils/db-utils.js
  function fetchProductById(id) {
    return new Promise((resolve, reject) => {
      db.get(`SELECT * FROM products WHERE id = ?`, [id], (err, row) => {
        if (err) reject(err);
        else resolve(row);
      });
    });
  }
  ```



