# Secure Web Application 🔒

A simple Node.js + Express app that demonstrates common security features and vulnerabilities.

## 🛡️ Features Implemented
- SQL Injection Protection
- Password Hashing with bcrypt
- Cross-Site Scripting (XSS) Prevention
- Role-Based Access Control (RBAC)
- HTTPS (TLS/SSL) Encryption

## 🚀 How to Run
1. Clone the repo
2. Run `npm install`
3. Run the app with: `node server.js`
4. Open in browser: `https://localhost:3000`

## 🧪 How to Test Security Features
- **SQL Injection**: Use `' OR '1'='1` in login (should be blocked)
- **XSS**: Submit `<script>alert("XSS")</script>` as a comment (should appear as text)
- **Admin Access**: Only users with role `admin` can open `/admin`
- **HTTPS**: Uses local cert.pem / key.pem (excluded via `.gitignore`)
