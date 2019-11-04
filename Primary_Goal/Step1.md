# Test public connectivity to Azure Storage 

1.	Using the URL and access token provided by the lab team, open a browser on your workstation and log into the Private Link Lab homesite. You will receive an email with lab guide details as well as additional details for use in your lab.  

2.	Go to “Virtual Machines” under the “Lab” section and copy the DNS name of VM-WIN-ON-PREM:
 
![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/1.1_2.png)

3.	On your lab workstation, open the Remote Desktop Connection app. 
- Before connecting to your VM, click “Show Options”
- Paste in the DNS name of your VM in the “Computer field”
- Enter the user name: “demouser” 
- Select “Allow me to save credentials” then hit “Connect”
- Enter the password: “demoPassword1!”
- Check the “Remember me” box, then click “OK”.
- On the certificate trust window, click the “Yes” button. 

4.	Accept the default privacy settings at login and close out any open windows and prompts.

5.	Once you at a clear desktop, search for Azure Storage Explorer using the search bar at the bottom, then launch the app.

6.	As the app launches, return to the lab home page open in your browser, and locate the “Storage Account Name” and “Storage Account Key” fields under the “Environmental Details” section: 

![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/1.1_6.png) 

- You will be copying both values to log into Azure Storage Explorer. 

7.	Once the Azure Storage Explorer has launched, the Connect to Azure Storage window should pop up. Else click the Connect icon (looks like a plug). 
- Ensure Add an Azure Account is selected.
- Choose “Use a storage account name and key” from the options menu below, then click next. 

 ![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/1.1_7.png)

8.	Copy in your “Storage Account Name” from the lab portal into both the Display Name and Account Name fields, and your “Storage Account Key” into the Account Key field, and click “Next”.

![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/1.1_8.png)

9.    On the Connection Summary window, click Connect

10.   Your storage account info should populate into the Explorer menu: 

![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/1.1_10.png)

11.   Click on the arrow next to your blob instance, labstorageXXXXXX (Key). 
- Right click Blob Containers and select Create Blob Container.  
- Name your container labcontainer. 
 
![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/1.1_11.png)

12. Locate the Image file on the desktop of your RDP session.
- Drag this into your lab container view window to upload, else use the Upload button. 

![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/1.1_12.png)

_Good work. You’ve created your blob container and tested connectivity over the Internet. You’re ready for the next task._ 
