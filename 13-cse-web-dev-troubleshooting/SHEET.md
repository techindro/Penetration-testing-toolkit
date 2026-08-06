# 🌐 Module 13: Web Development Troubleshooting & Debugging Guide

A comprehensive troubleshooting guide for common web development errors, environment bugs, database timeouts, and deployment issues in Full-Stack Computer Science projects.

---

## 🛑 1. CORS (Cross-Origin Resource Sharing) Errors

### Symptom:
`Access to fetch at 'http://localhost:5000/api' from origin 'http://localhost:3000' has been blocked by CORS policy.`

### Root Cause:
Browser security blocks client-side code from reading response data when origin (protocol + domain + port) differs between frontend and backend.

### Fixes:

#### Node.js / Express Backend Fix:
```javascript
const express = require('express');
const cors = require('cors');
const app = express();

// Allow specific origin or all origins during development
app.use(cors({
    origin: 'http://localhost:3000',
    credentials: true,
    methods: ['GET', 'POST', 'PUT', 'DELETE']
}));
```

---

## 📦 2. Node & NPM Version Conflicts / `node_modules` Bugs

### Symptom:
`npm ERR! code ERESOLVE` or `ERR_NODE_INVALID_PACKAGE_TARGET`

### Fixes:
```bash
# 1. Clean NPM Cache & Install with Legacy Peer Deps
npm cache clean --force
npm install --legacy-peer-deps

# 2. Hard Reset Node Modules
rm -rf node_modules package-lock.json  # On Linux/macOS
# On Windows PowerShell:
Remove-Item -Recurse -Force node_modules, package-lock.json
npm install

# 3. Use NVM (Node Version Manager) to switch Node versions
nvm install 18
nvm use 18
```

---

## 🗄️ 3. Database Connection Errors (MongoDB / PostgreSQL)

### MongoDB `MongooseServerSelectionError`:
- **Fix 1:** Check if `mongod` service is running: `sudo systemctl status mongod`
- **Fix 2:** Check MongoDB Atlas IP Whitelist: Go to Atlas -> Network Access -> Add IP `0.0.0.0/0` (for dev testing).

### PostgreSQL `password authentication failed for user "postgres"`:
```bash
# Switch to postgres user and reset password
sudo -u postgres psql
ALTER USER postgres WITH PASSWORD 'newpassword';
```

---

## 🔒 4. Environment Variables (`.env`) Not Loading

### Symptom:
`process.env.API_KEY` returns `undefined`.

### Fix:
```javascript
// Ensure dotenv is loaded at the VERY TOP of entry file (server.js / index.js)
require('dotenv').config();

// In Next.js / Vite:
// Prefix environment variables for client-side access:
// Next.js: NEXT_PUBLIC_API_KEY
// Vite: VITE_API_KEY
```
