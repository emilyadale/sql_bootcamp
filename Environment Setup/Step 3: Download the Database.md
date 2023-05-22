Database Download
======
Now that you have a functioning environment, it's time to download a test database and bring it into your environment. 


Step 1: Download the AdventureWorks Database
------
Navigate [here](https://learn.microsoft.com/en-us/sql/samples/adventureworks-install-configure?view=sql-server-ver16&tabs=ssms) and download the **AdventureWorksLT2022.bak** file. When you download this, take note of where the file is being saved. You will need this for later!


Step 2: Copy the Database to Docker
------
<img src="https://github.com/emilyadale/ru_databases/blob/43d4ab33f2063b159931e31fc94d4d21aa09098c/Environment%20Setup/Windows.png" width="25" height="25"> From the command line, enter this:

```
docker cp [Path to AdventureWorksLT2022.bak] BIA6203:/var/opt/mssql/data/ 
```
<img src="https://github.com/emilyadale/ru_databases/blob/43d4ab33f2063b159931e31fc94d4d21aa09098c/Environment%20Setup/Mac.png" width="25" height="25"> From the terminal, enter this:

```
sudo docker cp [Path to AdventureWorksLT2022.bak] BIA6203:/var/opt/mssql/data
```
Make sure you change [Path to AdventureWorksLT2022.bak] to the path where the file was saved. For example, I am on Mac and saved the database to my Downloads folder, so my command looks like: <br>
```sudo docker cp /Users/emilydale/Downloads/AdventureWorksLT2022.bak BIA6203:/var/opt/mssql/data```
If prompted for a password, use your administrator/machine password. 

Once the file is successfully copied to Docker, you may delete it from your machine. I recommend finishing the rest of these steps before deleting.

Step 3: Open Query Console
------
Back to Azure Data Studio! Right click on your newly-created database and select "New Query". 
This will open a new SQL file called SQLQuery_1 or something similar. 

Step 4: Get Database Information
------
In your SQLQuery_1 SQL file, run the following command: <br>
```RESTORE FILELISTONLY FROM DISK=N'/var/opt/mssql/data/AdventureWorksLT2022.bak';```

To run a query, you can highlight the query and either press the green arrow button in the top right corner or press F5. You may change keyboard shortcuts if you want to customize this later on. Check out [this page](https://learn.microsoft.com/en-us/sql/azure-data-studio/keyboard-shortcuts?view=sql-server-ver16) for instructions.

Your results will appear in a results window underneath your query window. Take note of the Logical and Physical Names as you will use those in the next section.
|LogicalName|	PhysicalName|	Type|
| ------------- |:-------------:| -----:|
AdventureWorksLT2022_Data|	C:\Program Files\Microsoft SQL Server\MSSQL16.MSSQLSERVER\MSSQL\DATA\ **AdventureWorksLT2012.mdf** |	D|
AdventureWorksLT2022_Log|	C:\Program Files\Microsoft SQL Server\MSSQL16.MSSQLSERVER\MSSQL\DATA\ **AdventureWorksLT2012_log.ldf** |	L|	


Step 5: Restore the Database
------
Still in your query window, use the results from the previous query to restore the database: <br>
```
RESTORE DATABASE AdventureWorks
FROM DISK=N'/var/opt/mssql/AdventureWorksLT2022.bak' WITH
MOVE 'AdventureWorksLT2022_Data' TO '/var/opt/mssql/data/AdventureWorksLT2012.mdf',
MOVE 'AdventureWorksLT2022_log' TO '/var/opt/mssql/data/AdventureWorksLT2012_log.ldf';
``` 

Note that the mdf and ldf file names came from the previous command.

Step 6: Verify the Connection
------
Now, double check that the AdventureWorks database is available.
1. Go to Connections and expand BIA6203 under Servers
2. Verify AdventureWorks is there


Now that you have successfully restored the database, you can continue on to Homework #1!

