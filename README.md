### Table of Contents
1. [Prerequisites](#1-prerequisites)
2. [Installation](#2-installation)

## 1. Prerequisites
Before installing rAthena there are certain tools and applications you will need which
differs between the varying operating systems available.

### Hardware
Hardware Type | Minimum | Recommended
------|------|------
CPU | 1 Core | 2 Cores
RAM | 1 GB | 2 GB
Disk Space | 300 MB | 500 MB

### Operating System & Preferred Compiler
Operating System | Compiler
------|------
Linux  | [gcc-7 or newer](https://www.gnu.org/software/gcc/gcc-7/) / [Make](https://www.gnu.org/software/make/)

### Required Applications
Application | Name
------|------
Database | [MariaDB 5 or newer](https://downloads.mariadb.org/)
Git | [Linux](https://git-scm.com/download/linux)

## 2. Installation 

### Full Installation Instructions

#### Create mysql user ragnarok

```bash
mysql -u username -p -e "CREATE USER 'ragnarok'@'localhost' IDENTIFIED BY 'ragnarok'"
```

#### Create the database
```bash
mysql -u username -p -e "CREATE DATABASE ragnarok";
```

#### Give user full privileges to the database
```bash
mysql -u username -p -e "GRANT SELECT,INSERT,UPDATE,DELETE,CREATE ON ragnarok.* TO 'ragnarok'@'localhost'";
```

#### Concat all sql in sql-files/
```bash
cat *.sql > complete.sql
```

#### Import the sql databases
````bash
import sql databases ``mysql -u username -p ragnarok < item_db.sql
````
````bash
import sql databases ``mysql -u username -p ragnarok < item_db_re.sql
````
````bash
import sql databases ``mysql -u username -p ragnarok < complete.sql
````

#### Install the required packages (make sure to use gcc/g++-7) form [rAthena Debian Page](https://github.com/rathena/rathena/wiki/Install-on-Debian)

#### Configure and create files needed to run server

````bash
chmod +x installserver
./installserver
````

#### Update conf import files for the specific server you're working on (default is for development server - snorlaxx)
Can do this by stashing your current settings, then pulling from git and re-applying your stash.

#### run rAthena
````bash
./athena-start start | stop
````