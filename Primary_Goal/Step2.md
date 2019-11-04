# Disable Public Connectivity on Azure Storage 

1.	Back in your browser session for the Azure Portal, on the __Home__ screen, select __Storage Accounts__, then select __labstorageXXXXXX__ 

2.	From the main menu of your storage account, find and select __Firewalls and Virtual Networks__.
- Change the __Allow Access from__ policy to __Selected Networks__.
- Leave all other fields blank, then click __Save__.
- This will automatically blacklist all public access to the lab storage account. 

![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/1.2_2.png)

3.	Return to your RDP session to VM-WIN-ON-PREM and try to download or open the __Image__ file in Storage Explorer.  
- You should see a failure message under the Activities window at the bottom.

![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/1.2_3.png)


### Well done, public access has been shut off to your storage account.  Time for the next task.
