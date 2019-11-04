# Shut off outbound Internet access to the spoke VM with an NSG and test

1.	Return to your Azure Portal, then go to __Home > Create a Resource__ and select it.

![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/2.2_1.png)
 
2.	Type in __“Network Security Group”__ in search bar and select the Network Security Group tile, then click __Create__ on the following screen. 

![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/2.2_2.png)

3.	Under the __Basics__ tab, input the following values, then click __Review + create__, then __Create__
- __Resource Group: ODL-Networking-XXXXXX__
- __Name: NSG_VM_WIN_SPOKE__
- __Region: West US 2__
 
![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/2.2_3.png)

4.	Once creation is complete, select __Go to Resource__

5.	Under the NSG menu, select __Inbound security rules__, click __+ Add__, then input the following values. Leave the rest in as default.
- __Destination: VirtualNetwork__
- __Destination port ranges: 3389__
- __Protocol: TCP__
- __Name: Allow_RDP__
- Then click __“Add”__
 
![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/2.2_5.png)

6.	Now select __Outbound Security Rules__, click __+ Add__, and enter the following values, leaving the rest default.
- __Destination: Service Tag__
- __Destination service tag: Internet__
- __Destination port ranges: *__
- __Name: Deny_Internet__
- Then click __“Add”__

![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/2.2_6.png)

7.	Next, select __Network Interfaces__, then click __+ Associate__.

![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/2.2_7.png)
 
8.	Locate and select the NIC with the name __vm-win-spokeXXX__

![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/2.2_8.png)

9.	Return to your RDP session for test client VM-WIN-SPOKE and to the following:
- Close the SSMS app
- Relaunch it (enter “SSMS” in the search bar if you need to)
- Log back in and note the results. You should be locked out:
 
![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/2.2_9.png)


### Good work, you have successfully blocked outbound Internet access for your VM in VNET_SPOKE.  On to the next task.
