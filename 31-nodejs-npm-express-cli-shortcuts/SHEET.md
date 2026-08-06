# 🟢 Module 31: Node.js, NPM & Express CLI Master Sheet (30 Commands)

Complete reference for 30 essential Node.js, NPM, NPX, and Express.js commands and code templates categorized by difficulty level (🟢 Easy, 🟡 Medium, 🔴 Hard).

---

## 🟢 Level 1: Easy / Beginner NPM & Node Commands (1 - 10)

```bash
# 1. Initialize new Node.js project with default package.json
npm init -y

# 2. Install production dependency
npm install express dotenv

# 3. Install development dependency (-D)
npm install -D nodemon typescript @types/node

# 4. Start Node.js application script
npm start

# 5. Run development script defined in package.json
npm run dev

# 6. Execute JavaScript file directly with Node
node index.js

# 7. Execute Node script with built-in auto-restart watching (--watch)
node --watch index.js

# 8. Check installed Node.js version
node -v

# 9. Check installed NPM CLI version
npm -v

# 10. List top-level installed NPM packages
npm list --depth=0
```

---

## 🟡 Level 2: Medium / Intermediate Package Management Commands (11 - 20)

```bash
# 11. Global NPM package installation
npm install -g pm2

# 12. Uninstall NPM package
npm uninstall express

# 13. Update all project packages to latest compatible versions
npm update

# 14. Execute NPX CLI package without global installation
npx kill-port 3000

# 15. Check project dependencies for known security vulnerabilities
npm audit

# 16. Automatically fix security vulnerabilities in dependencies
npm audit fix --force

# 17. Clean NPM package cache
npm cache clean --force

# 18. Install dependencies strictly from package-lock.json (CI/CD environments)
npm ci

# 19. Run PM2 process manager in background
pm2 start index.js --name "api-server"

# 20. View PM2 active processes and resource usage
pm2 status
```

---

## 🔴 Level 3: Hard / Advanced Node & Express Code Templates (21 - 30)

```javascript
// 21. Minimal Express.js HTTP Server Template (CJS)
const express = require('express');
const app = express();
app.use(express.json());

app.get('/api/health', (req, res) => res.json({ status: 'OK' }));

app.listen(3000, () => console.log('Server running on http://localhost:3000'));

// 22. Express.js Async Error Handler Middleware
app.use((err, req, res, next) => {
    console.error(err.stack);
    res.status(500).json({ error: 'Internal Server Error' });
});
```

```bash
# 23. View PM2 live logs
pm2 logs

# 24. Save PM2 process list to resurrect on server reboot
pm2 save

# 25. Generate PM2 startup script for Linux systemd
pm2 startup

# 26. Delete node_modules and reinstall clean dependencies
rm -rf node_modules package-lock.json && npm install

# 27. Run Node.js with increased Max V8 Memory Heap (4GB)
node --max-old-space-size=4096 index.js

# 28. Run Node.js inspector for Chrome DevTools debugging
node --inspect index.js

# 29. Outdated packages check
npm outdated

# 30. Link local NPM package for local package development
npm link
```
