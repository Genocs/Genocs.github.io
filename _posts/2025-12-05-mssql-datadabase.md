---
title: "MSSQL Database - Setup with Docker"
date: 2025-12-05
---

This guide walks you through setting up a Microsoft SQL Server database using Docker, creating tables, and populating them with sample data.

## Prerequisites

Before starting, ensure you have:
- Docker Desktop installed and running
- Docker Compose installed
- Basic knowledge of SQL and Docker

## Step 1: Create the Docker Compose file

Create a `docker-compose.yml` file to define the SQL Server container:

```yaml
version: '3.8'

services:
  sqlserver:
    image: mcr.microsoft.com/mssql/server:2022-latest
    container_name: sqlserver
    environment:
      - ACCEPT_EULA=Y
      - SA_PASSWORD=YourStrong@Passw0rd
      - MSSQL_PID=Developer
    ports:
      - "1433:1433"
    volumes:
      - sqlserver_data:/var/opt/mssql

volumes:
  sqlserver_data:
```

## Step 2: Start the SQL Server container

Navigate to the directory containing the `docker-compose.yml` file and run:

```bash
docker-compose up -d
```

This command starts the SQL Server container in detached mode.

## Step 3: Connect to the SQL Server instance

Use SQL Server Management Studio (SSMS) or Azure Data Studio to connect to the SQL Server instance. Use `localhost` as the server name and `sa` as the username. Enter the password you specified in the `docker-compose.yml` file.

## Step 4: Create a new database

Once connected, create a new database by running the following SQL command:

```sql
CREATE DATABASE SampleDB;
```

## Step 5: Create a new table

Create a new table in the `SampleDB` database:

```sql
USE SampleDB;

CREATE TABLE Employees (
    ID INT PRIMARY KEY NOT NULL,
    Name NVARCHAR(50),
    Position NVARCHAR(50),
    Salary DECIMAL(18, 2)
);
```

## Step 6: Insert sample data

Insert sample data into the `Employees` table:

```sql
INSERT INTO Employees (ID, Name, Position, Salary)
VALUES (1, 'John Doe', 'Software Engineer', 75000.00),
       (2, 'Jane Smith', 'Project Manager', 85000.00),
       (3, 'Sam Brown', 'Database Administrator', 70000.00);
```

## Step 7: Query the data

Query the data to verify the insertion:

```sql
SELECT * FROM Employees;
```

## Step 8: Backup the database

Backup the `SampleDB` database to a file:

```sql
BACKUP DATABASE SampleDB
TO DISK = '/var/opt/mssql/data/SampleDB.bak';
```

## Step 9: Restore the database

To restore the database from the backup file, run:

```sql
RESTORE DATABASE SampleDB
FROM DISK = '/var/opt/mssql/data/SampleDB.bak'
WITH MOVE 'SampleDB_Data' TO '/var/opt/mssql/data/SampleDB.mdf',
MOVE 'SampleDB_Log' TO '/var/opt/mssql/data/SampleDB.ldf';
```

## Step 10: Stop and remove the container

When you're done, stop and remove the container with:

```bash
docker-compose down
```

## Conclusion

You have successfully set up a Microsoft SQL Server database using Docker, created tables, populated them with sample data, and learned how to backup and restore the database.
