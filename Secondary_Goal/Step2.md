# Shut off outbound Internet access to the spoke VM with an NSG and test

1.	Return to your Azure Portal, then go to Home > Create a Resource and select it.

![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/2.2_1.png)
 
2.	Type in “Network Security Group” in search bar and select the Network Security Group tile, then click Create on the following screen. 

![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/2.2_2.png)

3.	Under the Basics tab, input the following values, then click Review + create, then Create
- Resource Group: ODL-Networking-XXXXXX
- Name: NSG_VM_WIN_SPOKE
- Region: West US 2
 
![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/2.2_3.png)

4.	Once creation is complete, select Go to Resource

5.	Under the NSG menu, select Inbound security rules, click + Add, then input the following values. Leave the rest in as default.
- Destination: VirtualNetwork
- Destination port ranges: 3389
- Protocol: TCP
- Name: Allow_RDP
- Then click “Add”
 
![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/2.2_5.png)

6.	Now select Outbound Security Rules, click + Add, and enter the following values, leaving the rest default.
- Destination: Service Tag
- Destination service tag: Internet
- Destination port ranges: * 
- Name: Deny_Internet
- Then click “Add”

![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/2.2_6.png)

7.	Next, select Network Interfaces, then click + Associate.

![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/2.2_7.png)
 
8.	Locate and select the NIC with the name vm-win-spokeXXX

![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/2.2_8.png)

9.	Return to your RDP session for test client VM-WIN-SPOKE and to the following:
- Close the SSMS app
- Relaunch it (enter “SSMS” in the search bar if you need to)
- Log back in and note the results. You should be locked out:
 
![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/2.2_9.png)


__Good work, you have successfully blocked outbound Internet access for your VM in VNET_SPOKE.  On to the next task.__
