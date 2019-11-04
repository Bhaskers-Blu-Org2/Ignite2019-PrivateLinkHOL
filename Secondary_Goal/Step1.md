# Test public connectivity to Azure SQL 

1.	In your lab portal, go to __Virtual Machines__ and copy the DNS name of __VM-WIN-SPOKE__:

![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/2.1_1.png)

2.	On your lab workstation, open the Remote Desktop Connection app. 
- __Before connecting__ to your VM, click “Show Options”
- Paste in the DNS name of your VM in the “Computer field”
- Enter the __user name: “demouser”__ 
- Select “Allow me to save credentials” then hit “Connect”
- Enter the __password: “demoPassword1!”__
- Check the “Remember me” box, then click “OK”.
- On the certificate trust window, click the “Yes” button.

3.	Accept the default privacy settings at login and close out any open windows and prompts.

4.	From the search bar on the desktop, search for __“SSMS”__ then launch Microsoft SQL Server Management Studio.

5.	As SSMS launches, return to the lab portal and under “Environmental Details”, locate “SQL Server Name”, “SQL Server Username”, and “SQL Server Password”.

![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/2.1_5.png)

6.	Using the values above, into your Azure SQL server from SMSS, using “SQL Server Authentication” mode from the drop-down menu: 
  
![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/2.1_6.png)

7.	After logging in, open __Databases > labsqldb > Tables__, Right click Tables, and select __New Table__. 

![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/2.1_7.png)

8.	Create a columns named, test1, test2 and test 3 and leave the data type to nchar(10).

![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/2.1_8.png)

9.	Go to File > Save Table_1 (or hit Ctrl + s) and save out your table as __“Table_1”__. 
 
![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/2.1_9.png)
 

### Nice work, you’ve just tested your Azure SQL DB using public connectivity from an Azure VM. Time for the next task.
