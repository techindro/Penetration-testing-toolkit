# 🗄️ Module 15: Database CLI Shortcuts (PostgreSQL, MySQL, MongoDB, Redis)

Essential database command line shortcuts and queries for PostgreSQL, MySQL, MongoDB, and Redis with clear practical examples.

---

## 🐘 1. PostgreSQL (`psql`) CLI Commands

```bash
# Example 1: Connect to database as user postgres
psql -U postgres -d my_database

# Example 2: Meta-Commands inside psql prompt:
\l          # List all databases
\c app_db   # Connect to database 'app_db'
\dt         # List all tables in current database
\d users    # Describe schema/columns of 'users' table
\q          # Quit/Exit psql shell
```

---

## 🐬 2. MySQL / MariaDB CLI Commands

```bash
# Example 1: Connect to local MySQL database with password prompt
mysql -u root -p app_database

# Example 2: Useful SQL commands:
SHOW DATABASES;
USE app_database;
SHOW TABLES;
DESCRIBE users;
```

---

## 🍃 3. MongoDB (`mongosh`) Shell Commands

```javascript
// Connect to local MongoDB instance
mongosh "mongodb://localhost:27017/app_db"

// MongoDB Shell Commands:
show dbs                        // List all databases
use app_db                      // Switch database
show collections                // List collections (tables)
db.users.find().pretty()        // Query all documents nicely formatted
db.users.find({ status: "active" }) // Query documents with filter
```

---

## 🔴 4. Redis (`redis-cli`) Commands

```bash
# Connect to Redis server
redis-cli

# Core Redis Key-Value Commands:
PING                    # Returns PONG (Connection test)
SET user:101 "Rahul"    # Store Key-Value pair
GET user:101            # Output: "Rahul"
KEYS *                  # List all stored keys
FLUSHALL                # Danger: Clear ALL stored keys in memory
```
