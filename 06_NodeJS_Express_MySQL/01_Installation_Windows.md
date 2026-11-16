# 01. Install Node.js, VS Code and MySQL

## Install Node.js
1. Download the LTS installer from https://nodejs.org/
2. Run the Windows installer and keep the Add to PATH option enabled.
3. Reopen PowerShell or VS Code terminal.
4. Verify:

```powershell
node --version
npm --version
```

Both commands should return version numbers.

## Install VS Code
Download from https://code.visualstudio.com/. Useful extensions include Prettier, ESLint and REST Client.

## Install MySQL
1. Download MySQL Installer from https://dev.mysql.com/downloads/installer/
2. Install MySQL Server and optionally MySQL Workbench.
3. Configure it as a development server.
4. Use port `3306` unless that port is occupied.
5. Set a strong root password.
6. Configure MySQL as a Windows service and start it.

Open MySQL Workbench and connect to the local server. Verify:

```sql
SELECT VERSION();
```

## Create the practice database

```sql
CREATE DATABASE arinfotek_db
  CHARACTER SET utf8mb4
  COLLATE utf8mb4_unicode_ci;
```

**Exercise:** Record Node.js, npm and MySQL versions. Create `arinfotek_db`.
