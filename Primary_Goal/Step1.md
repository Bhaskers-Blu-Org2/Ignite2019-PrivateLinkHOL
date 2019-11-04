# Test public connectivity to Azure Storage 

1.	Using the URL and access token provided by the lab team, open a browser on your workstation and log into the Private Link Lab homesite. You will receive an email with lab guide details as well as additional details for use in your lab.  

2.	Go to “Virtual Machines” under the “Lab” section and copy the DNS name of __VM-WIN-ON-PREM__:
 
![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/1.1_2.png)

3.	On your lab workstation, open the Remote Desktop Connection app. 
- __Before connecting__ to your VM, click “Show Options”
- Paste in the DNS name of your VM in the “Computer field”
- Enter the __user name: “demouser”__ 
- Select “Allow me to save credentials” then hit “Connect”
- Enter the __password: “demoPassword1!”__
- Check the “Remember me” box, then click “OK”.
- On the certificate trust window, click the “Yes” button. 

4.	Accept the default privacy settings at login and close out any open windows and prompts.

5.	Once you at a clear desktop, search for __Azure Storage Explorer__ using the search bar at the bottom, then launch the app.

6.	As the app launches, return to the lab home page open in your browser, and locate the “Storage Account Name” and “Storage Account Key” fields under the “Environmental Details” section: 

![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/1.1_6.png) 

- You will be copying both values to log into Azure Storage Explorer. 

7.	Once the Azure Storage Explorer has launched, the __Connect to Azure Storage__ window should pop up. Else click the __Connect__ icon (looks like a plug). 
- Ensure __Add an Azure Account__ is selected.
- Choose __“Use a storage account name and key”__ from the options menu below, then click next. 

 ![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/1.1_7.png)

8.	Copy in your “Storage Account Name” from the lab portal into both the __Display Name__ and __Account Name__ fields, and your “Storage Account Key” into the __Account Key__ field, and click “Next”.

![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/1.1_8.png)

9.    On the __Connection Summary__ window, click __Connect__

10.   Your storage account info should populate into the __Explorer menu__: 

![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/1.1_10.png)

11.   Click on the arrow next to your blob instance, __labstorageXXXXXX (Key)__. 
- Right click __Blob Containers__ and select __Create Blob Container__.  
- Name your container __labcontainer__. 
 
![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/1.1_11.png)

12. Locate the __Image__ file on the desktop of your RDP session.
- Drag this into your lab container view window to upload, else use the __Upload__ button. 

![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/1.1_12.png)


### Good work. You’ve created your blob container and tested connectivity over the Internet. You’re ready for the next task.
