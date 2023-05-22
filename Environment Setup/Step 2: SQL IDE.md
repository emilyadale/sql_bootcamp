SQL IDE
======
Now that Docker is set up, we need to install and prepare an IDE, or integrated development environment. This allows us to interact with our database in a user-friendly environment.
There are many choices for a SQL IDE. In this class, we will use VS Code, which is available for both Mac and Windows.

Step 1: Install VS Code
------
Navigate [here](https://code.visualstudio.com/Download) and download the appropriate VS Code version for your machine. This is a free download. 

Step 2: Open VS Code
------
Open the application you just downloaded to ensure it is functioning correctly. You will see something like this:

<img src="https://github.com/emilyadale/ru_databases/blob/b556a073f47144de2d138b4e9081e043fa1e3011/Environment%20Setup/VS%20Code.png" width="500"> <br>
You may customize the look of VS Code from this Welcome section, but you don't have to go through each welcome step.


Step 3: Add Extensions
------
Next, we need to add extensions to VS Code to ensure it runs correctly.

1. Navigate to **Extensions** on the left side of your VS Code window. It is the icon that looks like Tetris.
2. Next, search for the Docker extension and click install.
3. Search for the SQL Server (mssql) extension and click install.

Step 4: Connect VS Code to Docker
------
Click on the newly created SQL Server extension on the left side of your VS Code window. It is the icon that looks like a rectangle and should be at the bottom.
1. Click "Add Connection" from the Connections screen
2. You will be prompted to enter each part of the authentication in a text box, one item at a time. Press **enter** after each item:
* server: localhost;1401 (Note: if your port number was different in the Docker setup, change to the port specified.)
* database: leave blank
* Authentication Type: SqlLogin
* User: SA
* Password: Password1!
* Save Password: Yes
* Profile Name: BIA6203
3. Connection results will be in the lower right side of your screen. 

<img src="https://github.com/emilyadale/ru_databases/blob/135d12de0f9101d80a140b9463da079962211a5b/Environment%20Setup/gearRed.png" width="50" height="50"> **Troubleshooting Tips:** <br>
* Connection error? Make sure your Docker container is up and running each time you use VS Code. <br>


Step 4: Verify Docker is Running
------
Still in the command line/terminal: (same for both Windows and Mac): <br>
``` docker ps -a``` <br>

<img src="https://github.com/emilyadale/ru_databases/blob/88867e6fe5d70bd2e54bc8bd87f7e4b61b1cf5a4/Environment%20Setup/DockerPort.png">
