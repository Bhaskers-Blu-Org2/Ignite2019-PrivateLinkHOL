# Configure Private Link + private DNS to Azure SQL and link VNET_SPOKE to the private zone.

1.	Back in your Azure portal session, go to Home > Create a Resource.

2.	Using the search bar, enter “Private Link” and click the tile.

![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/2.3_2.png) 

3.	On the next page, click Create to begin the Private Link configuration wizard.

4.	At the Private Link Center, select Private endpoints then click + Add.

![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/2.3_4.png) 
 
5.	Under the Basics tab, enter the following values:
- Resource Group: ODL-networking-XXXXXX
- Name: labsql
- Region: West US 2
- Then click Next: Resource >

![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/2.3_5.png) 

6.	Under the Resource tab, enter the following values:
- Resource type: Microsoft.Sql/servers
- Resource: labsqlXXXXXX
- Target sub-resource: sqlServer
- Then click “Next: Configuration >”
 
![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/2.3_6.png)

7.	Under the Configuration tab, enter the following values:
- Virtual Network: VNET_HUB
- Subnet: SUBNET_PRIVATE_LINK
- Intergrate with private DNS zone: Yes
- Private DNS Zone: privatelink.database.windows.net
- Then click Review + create

![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/2.3_7.png) 

8.	On the final validation page, click Create.  When creation is complete, select Go to resource.
- Take a note of the Private IP, it should be 192.168.16
- Similar to the storage example, the public vanity name is “labsqlXXXXXX.database.windows.net”

9.	Now it’s time to register the spoke to the new private zone. Go back to Home > Resource Groups and select the ODL-networking-XXXXXX resource group. 

10.	Using the filter bar, type in “Privatelink” and select the zone privatelink.database.windows.net.

![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/2.3_10.png) 

11.	Under Settings select Virtual Network links the click + Add

![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/2.3_11.png) 
 
12.	On the Add Virtual network link blade, enter the following values:
- Link name: VNet-spoke
- Virtual Network: VNET_SPOKE
- Then click OK 

![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/2.3_12.png) 


__Nice work. We are now ready for the final task!__
