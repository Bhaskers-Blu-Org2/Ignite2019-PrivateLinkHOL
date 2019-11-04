# Disable Public Connectivity on Azure Storage 

1.	Back in your browser session for the Azure Portal, on the Home screen, select Storage Accounts, then select labstorageXXXXXX 

2.	From the main menu of your storage account, find and select Firewalls and Virtual Networks.
- Change the Allow Access from policy to Selected Networks.
- Leave all other fields blank, then click Save.
- This will automatically blacklist all public access to the lab storage account. 

![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/1.2_2.png)

3.	Return to your RDP session to VM-WIN-ON-PREM and try to download or open the Image file in Storage Explorer.  
- You should see a failure message under the Activities window at the bottom.

![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/1.2_3.png)


__Well done, public access has been shut off to your storage account.  Time for the next task.__
