---
title: "MS SQL Database - Data Governance and Management"
date: 2025-12-11
---

## Microsoft SQL Server - Data Governance and Management

This post contains useful information about how to setup your local environment to work efficiently with Microsoft SQL server.

There are many ways to setup your environment, but the most efficient way is to use containers.

In this post we will cover the following topics:
- Working with Containers
- How to restore a backup


### Working with Containers

The best way to start working with SQL server is to setup a containerized environment. There will be a lot benefit on doing that:
- Setup your enviroment locally (no external dependecies, no fear to break other team work)
- Speedup the setup (Just pull the image and run the container)
- Easy to teardown (just remove the container when you are done)

### How to restore a backup

Now let suppose you have a backup file of a database and you want to restore it into your SQL Server container.
Follow the steps illustrated below will guide you to restore a backup file into your SQL Server container.

#### References

Before you start, please check the following reference that will help you to understand better the process:

[restoring-adventureworks-database](https://www.linkedin.com/pulse/restoring-adventureworks-database-sql-servercontainer-daniel-anselmo-qgpwf/)

Please before you start, make sure you have the following prerequisites:
- Docker installed and running
- SQL Server container up and running
- Backup file available (for this example we will use AdventureWorks2025.bak)

You can run the following commands to restore the backup file into your SQL Server container. When the commands are executed you can proceed to restore the database. You can so by using SQL Server Management Studio (SSMS) or Azure Data Studio to connect to the SQL Server instance running inside the container and execute the restore command.


```bash
# 1. Pull the latest SQL Server image
docker pull mcr.microsoft.com/mssql/server:2025-latest

# 2. Check that container is up and running
docker ps

# 3. Copy the file to the container
docker cp c/dev/db_backup/aw/AdventureWorks2025.bak sqlserver:/var/opt/mssql/data/
```

```bash
# 4. TO BE TESTED: Export the container's data volume to a tar file outside the container
docker run --rm --volumes-from sqlserver -v $(pwd):/backup busybox tar cvf /backup/backup.tar /var/opt/mssql/data
```

```sql
-- Connect to the SQL Server instance
-- Restore the database from the backup file
RESTORE DATABASE AdventureWorks2025
FROM DISK = '/var/opt/mssql/data/AdventureWorks2025.bak'
WITH MOVE 'AdventureWorks2025_Data' TO '/var/opt/mssql/data/AdventureWorks2025.mdf',
MOVE 'AdventureWorks2025_Log' TO '/var/opt/mssql/data/AdventureWorks2025.ldf';
```
