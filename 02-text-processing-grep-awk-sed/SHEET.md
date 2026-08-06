# 📝 Module 02: Text Processing & Log Filtering Commands (`grep`, `awk`, `sed`)

Quick-reference cheat-sheet for manipulating strings, parsing log files, and extracting data pipelines using Linux CLI utilities.

---

## 🔎 1. Searching Text with `grep`

```bash
# Search recursively for string in files with line numbers
grep -rn "API_KEY" /var/www/

# Case-insensitive search
grep -ri "password" /etc/

# Search and invert match (show lines NOT containing pattern)
grep -v "DEBUG" server.log

# Show 3 lines of context BEFORE (-B) and AFTER (-A) match
grep -C 3 "ERROR" access.log

# Count matching occurrences
grep -c "404" access.log
```

---

## 📐 2. Column Extraction with `awk`

```bash
# Print 1st and 3rd column (default whitespace delimiter)
awk '{print $1, $3}' access.log

# Specify custom delimiter (e.g. colon ':') and print 1st field
awk -F ':' '{print $1}' /etc/passwd

# Filter lines where 3rd column value is greater than 500
awk '$3 > 500 {print $1, $3}' data.txt

# Print last column of every line
awk '{print $NF}' file.txt
```

---

## ✏️ 3. Inline Replacement & Editing with `sed`

```bash
# Replace first occurrence of 'http' with 'https' per line
sed 's/http/https/' file.txt

# Replace ALL occurrences globally per line ('g')
sed 's/http/https/g' file.txt

# Modify file in-place ('-i')
sed -i 's/127.0.0.1/localhost/g' config.env

# Delete blank lines from file
sed -i '/^$/d' file.txt
```

---

## 🔀 4. Sorting, Deduplicating & Cutting (`sort`, `uniq`, `cut`)

```bash
# Deduplicate lines (must sort before running uniq!)
sort urls.txt | uniq > unique_urls.txt

# Count frequency of duplicate entries
sort access.log | uniq -c | sort -nr

# Extract comma-delimited columns (e.g. 2nd field)
cut -d ',' -f 2 data.csv
```
