Setup Instructions
======
In order to be able to run SQL on your local machine, you need three things:
1. Somewhere to host a database
2. An IDE in which to query the database
3. A database

These instructions will guide you through each step in the process. Make sure to follow them in order to avoid any issues.

Before starting these instructions, make sure you have the following:
------
1. Know your computer type, model, and OS version. Macs and Window machines run slightly differently!
   I have designated system-specific instructions using the following logos:
   ![Windows](https://github.com/emilyadale/ru_databases/blob/43d4ab33f2063b159931e31fc94d4d21aa09098c/Environment%20Setup/Windows.png)
   ![Mac](https://github.com/emilyadale/ru_databases/blob/43d4ab33f2063b159931e31fc94d4d21aa09098c/Environment%20Setup/Mac.png)
3. Ensure you have administrative permissions on your machine
4. If you run into trouble, ask for help in our Course Q&A discussion. Make sure to note which section and step you are on.

Docker Set Up
======
Docker is a software that will enable you to create containers (think Virtual Machines, but better). This will be used each time you want to use your database.

Step 1: Install Docker
------
Navigate  [here](https://docs.docker.com/get-docker/) and download the appropriate Docker version for your machine. This is a free download. You may sign up for an account if you want, but it is not necessary.

Step 2: Open Docker
------
Open the application you just downloaded to ensure it is functioning correctly. You will see something like this:

![Docker]((https://github.com/emilyadale/ru_databases/blob/43d4ab33f2063b159931e31fc94d4d21aa09098c/Environment%20Setup/Docker_Home.png))


Step 2: Download SQL Server Docker Image
------
Next, we need to download the SQL Server Docker Image, which is a file used to execute code in Docker. Open the **command line** (also called the **terminal** on Mac). 

![Windows](https://github.com/emilyadale/ru_databases/blob/43d4ab33f2063b159931e31fc94d4d21aa09098c/Environment%20Setup/Windows.png)
From the command line, enter this:
```
docker pull mcr.microsoft.com/mssql/server:latest
```
![Mac](https://github.com/emilyadale/ru_databases/blob/43d4ab33f2063b159931e31fc94d4d21aa09098c/Environment%20Setup/Mac.png)
From the terminal, enter this:
```
sudo docker pull mcr.microsoft.com/mssql/server:latest
```


Step 3: Run Container Image with Docker
------

Step 4: Verify Docker is Running
------
