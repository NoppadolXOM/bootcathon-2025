# Setup: Local MySQL Database with Chinook Sample Data
This guide walks you through setting up a **local MySQL database** and importing the **Chinook** sample dataset. This database is intended to be used for testing AI SQL agents, such as in n8n.

## Requirements
- MySQL installed locally (macOS, Linux, or Windows)
- A terminal or shell
- `Chinook_MySql.sql` file located in your project under:
  ```
  ./data/Chinook_MySql.sql
  ```

## Step 1: Install MySQL
### macOS (Homebrew)
```bash
brew install mysql
brew services start mysql
```
### Ubuntu / Debian
```bash
sudo apt update
sudo apt install mysql-server
sudo systemctl start mysql
```
### Windows
- Download and install from: https://dev.mysql.com/downloads/mysql/

## Step 2: Import the Chinook Data
Download or place the SQL file at:
```
./data/Chinook_MySql.sql
```
Run the following command from your project root:
```bash
mysql -u root -p chinook < data/Chinook_MySql.sql
```
## Step 3: Verify the Import
Connect to the database:
```bash
mysql -u root -p chinook
```
Then run:
```sql
SHOW TABLES;
SELECT * FROM Customer LIMIT 5;
```
You should see tables like `Album`, `Artist`, `Customer`, etc.

## 🔗 References
- Chinook DB GitHub: https://github.com/lerocha/chinook-database
- MySQL Docs: https://dev.mysql.com/doc/