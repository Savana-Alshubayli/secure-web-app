# 🔐 Secure Web App

This project is a secure Node.js + Express web application that demonstrates common web vulnerabilities and how to fix them. It includes examples of both **vulnerable** and **secure** implementations.

---

## 🛠 Features Demonstrated

### ✅ Implemented Vulnerabilities + Fixes:

| Feature                             | Vulnerable Version | Fixed Version ✅ |
|-------------------------------------|---------------------|------------------|
| SQL Injection (Login & Register)    | Yes                 | ✅ Parameterized queries (SQLite) |
| Weak Password Storage (MD5)         | Yes                 | ✅ Switched to bcrypt |
| Cross-Site Scripting (XSS)          | Yes                 | ✅ Output is escaped in templates |
| Role-Based Access Control (RBAC)    | No control          | ✅ Only admin sees `/admin` page |
| TLS/SSL Encryption (HTTPS)          | Not encrypted       | ✅ Enabled using `cert.pem` and `key.pem` |

---

## 🚀 How to Run Locally

1. Clone the project:
   ```bash
   git clone https://github.com/Savana-Alshubayli/secure-web-app.git
   ```

2. Navigate into the project:
   ```bash
   cd secure-web-app
   ```

3. Install dependencies:
   ```bash
   npm install
   ```

4. Start the HTTPS server:
   ```bash
   node server.js
   ```

5. Open in browser:  
   👉 [https://localhost:3000](https://localhost:3000)

---

## 🧪 How to Test Each Security Feature

### 🔸 SQL Injection Test (Login)
- Try entering:
  - **Username**: `' OR '1'='1`
  - **Password**: anything
- ❌ Should not let you in if secure version is used.

---

### 🔸 Weak Password Storage (MD5 → bcrypt)
- Older users have MD5-hashed passwords.
- New users are stored with bcrypt.
- View in database:
  ```sql
  SELECT username, password FROM users;
  ```
- You’ll see bcrypt hashes start with `$2b$10...`.

---

### 🔸 XSS Test
- Go to `/dashboard`
- Submit a comment like:
  ```html
  <script>alert("Hacked!")</script>
  ```
- ❌ If vulnerable: alert box pops up.  
- ✅ If fixed: tag is shown as text.

---

### 🔸 Access Control (RBAC)
- Only users with `role = 'admin'` can access `/admin`
- All others get:
  ```
  Forbidden – Admins only!
  ```

---

### 🔸 HTTPS Test
- Project uses:
  - `cert.pem`
  - `key.pem`
- You should see:  
  `🔒 HTTPS server running at https://localhost:3000/`

> ⚠️ Do not upload private keys or database files to GitHub.

---

## 📂 .gitignore

Ensure the following files are excluded:

```
node_modules/
cert.pem
key.pem
.env
database.db
```

---

## 👩‍💻 Built With

- Node.js
- Express.js
- SQLite3
- bcrypt
- Pug (template engine)

---

## 📄 License

This project is for educational purposes and does not include production-level security.
