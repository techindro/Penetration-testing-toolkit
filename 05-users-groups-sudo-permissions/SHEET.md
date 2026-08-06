# 👥 Module 05: Users, Groups & Sudo Privileges Commands

Quick-reference cheat-sheet for managing system users, adding permissions, environment groups (`docker`, `dialout`, `sudo`), and inspecting user privileges.

---

## 👤 1. User & Identity Commands (`whoami`, `id`, `useradd`)

```bash
# Print current logged-in user
whoami

# Display UID, GID, and assigned group memberships
id

# Add new system user
sudo useradd -m -s /bin/bash newuser

# Set or reset user password
sudo passwd newuser
```

---

## 👥 2. Group Management (`usermod` & `groups`)

```bash
# Add user to a group (e.g. docker, dialout, sudo)
sudo usermod -aG docker $USER
sudo usermod -aG dialout $USER
sudo usermod -aG sudo newuser

# View groups assigned to user
groups $USER

# Remove user from group
sudo gpasswd -d username groupname
```

---

## 🛡️ 3. Sudo Privileges & Security Auditing (`sudo`, `/etc/sudoers`)

```bash
# List allowed (and forbidden) commands for current user
sudo -l

# Edit sudoers configuration file safely (Visudo)
sudo visudo

# Add user entry in visudo for passwordless execution:
# username ALL=(ALL:ALL) NOPASSWD: ALL
```
