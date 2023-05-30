SQL IDE
======
Now that Docker is set up, we need to install and prepare an IDE, or integrated development environment. This allows us to interact with our database in a user-friendly environment.
There are many choices for a SQL IDE. In this class, we will use Azure Data Studio, which is available for both Mac and Windows.

Step 1: Install Azure Data Studio
------
Navigate [here](https://learn.microsoft.com/en-us/sql/azure-data-studio/download-azure-data-studio?view=sql-server-ver16&tabs=redhat-install%2Credhat-uninstall) and download the appropriate Azure Data Studio version for your machine. This is a free download. 


Step 2: Connect Azure Data Studio to Docker
------
Now we need to point our SQL IDE to Docker so it knows where the database will be hosted.

1. Click on the Connections tab on the left side of your screen. 
2. Click on the Add Connection button at the top - this looks like the Connections icon with a + sign
3. The connection window will appear on the right side of your screen. Enter the following information:
* Connection type: Microsoft SQL Server - Make sure Parameters is checked
* Server: localhost, 1401 (note, the 1401 is the port number from the Docker setup)
* Authentication Type: SQL Login
* User: SA
* Password: Password1!
* Remember Password: Check Yes to prevent logging in each time
* Database: Leave at Default
* Name: Whatever you want to call this. I will call mine BIA 6203
If you get a message asking you to Enable Trust Server Certificate, enable it.

<img src="https://github.com/emilyadale/ru_databases/blob/135d12de0f9101d80a140b9463da079962211a5b/Environment%20Setup/gearRed.png" width="50" height="50"> **Troubleshooting Tips:** <br>
* Connection error? Make sure your Docker container is up and running each time you use VS Code. <br>


Step 3: Verify your Connection
------
After a successful connection, you should see your newly-named database on the left side of your screen under Servers.
