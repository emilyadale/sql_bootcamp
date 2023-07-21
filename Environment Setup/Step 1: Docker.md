Docker Set Up
======
Docker is a software that will enable you to create containers (think Virtual Machines, but better). This will be used each time you want to use your database.

Step 1: Install Docker
------
Navigate [here](https://docs.docker.com/get-docker/) and download the appropriate Docker version for your machine. This is a free download. You may sign up for an account if you want, but it is not necessary.

Step 2: Open Docker
------
Open the application you just downloaded to ensure it is functioning correctly. You will see something like this:

<img src="https://github.com/emilyadale/ru_databases/blob/43d4ab33f2063b159931e31fc94d4d21aa09098c/Environment%20Setup/Docker_Home.png" width="500"> <br>


Step 3: Download SQL Server Docker Image
------
Next, we need to download the SQL Server Docker Image, which is a file used to execute code in Docker. Open the **command line** (also called the **terminal** on Mac). 

<img src="https://github.com/emilyadale/ru_databases/blob/43d4ab33f2063b159931e31fc94d4d21aa09098c/Environment%20Setup/Windows.png" width="25" height="25"> From the command line, enter this:

```
docker pull mcr.microsoft.com/mssql/server:latest
```
<img src="https://github.com/emilyadale/ru_databases/blob/43d4ab33f2063b159931e31fc94d4d21aa09098c/Environment%20Setup/Mac.png" width="25" height="25"> From the terminal, enter this:

```
sudo docker pull mcr.microsoft.com/mssql/server:latest
```
If you are prompted for the password, this is your administrator/machine password.

Step 4: Run Container Image with Docker
------
Still in the command line/terminal: <br>

<img src="https://github.com/emilyadale/ru_databases/blob/43d4ab33f2063b159931e31fc94d4d21aa09098c/Environment%20Setup/Windows.png" width="25" height="25"> From the command line, enter this:
```
docker run -e "ACCEPT_EULA=Y" -e MSSQL_SA_PASSWORD=Password1! --name "RUBootcamp" -p 1401:1433 -v sql1data:/var/opt/mssql -d mcr.microsoft.com/mssql/server:latest
```

<img src="https://github.com/emilyadale/ru_databases/blob/43d4ab33f2063b159931e31fc94d4d21aa09098c/Environment%20Setup/Mac.png" width="25" height="25"> From the terminal, enter this:

```
sudo docker run -e 'ACCEPT_EULA=Y' -e 'MSSQL_SA_PASSWORD=Password1!' --name 'RUBootcamp' -p 1401:1433 -v sql1data:/var/opt/mssql -d mcr.microsoft.com/mssql/server:latest
```
If you are prompted for a password, this is your administrator/machine password. 

<img src="https://github.com/emilyadale/ru_databases/blob/135d12de0f9101d80a140b9463da079962211a5b/Environment%20Setup/gearRed.png" width="50" height="50"> **Troubleshooting Tips:** <br>
* If you receive an error like ``` event not found: ' ```  you might need to manually type the quotation marks as copy/paste sometimes does some odd things. <br>
* If you have a newer Mac with the M1 OS and you receive an error, change the above command in the terminal to: <br>
```sudo docker run -e 'ACCEPT_EULA=Y' -e 'MSSQL_SA_PASSWORD=Password1!' --name 'RUBootcamp' -p 1401:1433 -v sql1data:/var/opt/mssql -d mcr.microsoft.com/azure-sql-edge:1.0.6```


Step 5: Verify Docker is Running
------
Still in the command line/terminal: (same for both Windows and Mac): <br>
``` docker ps -a``` <br>

<img src="https://github.com/emilyadale/ru_databases/blob/88867e6fe5d70bd2e54bc8bd87f7e4b61b1cf5a4/Environment%20Setup/DockerPort.png">
