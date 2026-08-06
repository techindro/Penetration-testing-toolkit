# 📁 Module 01: Linux File System, Search & Permission Commands

A quick-reference cheat-sheet for Linux file management, searching, archiving, and SUID permission bits that engineering students often forget.

---

## 🔍 1. Finding Files (`find` & `locate`)

```bash
# Find files by exact name
find /path/to/dir -name "filename.txt"

# Find files case-insensitively
find /path/to/dir -iname "*.log"

# Find files modified in the last 24 hours (1 day)
find /var/log -mtime -1

# Find files larger than 100MB
find / -size +100M 2>/dev/null

# Find SUID binaries (Files executing with root privileges)
find / -perm -4000 -type f 2>/dev/null

# Find SGID binaries
find / -perm -2000 -type f 2>/dev/null
```

---

## 🔒 2. File Permissions & Ownership (`chmod` & `chown`)

### Permission Octal Value Chart:
- `4` = Read (`r`)
- `2` = Write (`w`)
- `1` = Execute (`x`)

```bash
# Standard permissions (Owner: rwx, Group: r-x, Others: r-x)
chmod 755 script.sh

# Restrict to Owner only (Owner: rw-, Group: ---, Others: ---)
chmod 600 id_rsa

# Add execution permission to owner
chmod u+x script.sh

# Change owner and group recursively
chown -R username:groupname /var/www/html/

# Set SUID bit (4000)
chmod 4755 /usr/local/bin/custom_binary
```

---

## 📦 3. Archiving & Compression (`tar`, `zip`, `gzip`)

```bash
# Create a tar.gz compressed archive
tar -czvf archive.tar.gz /path/to/folder/

# Extract a tar.gz archive
tar -xzvf archive.tar.gz -C /target/dir/

# Unzip zip file
unzip archive.zip -d /target/dir/
```

---

## 📊 4. Disk & Storage Inspection (`df`, `du`, `stat`)

```bash
# View human-readable disk space usage
df -h

# View directory size summary
du -sh /var/log/*

# View detailed file metadata & inode info
stat /etc/passwd
```
