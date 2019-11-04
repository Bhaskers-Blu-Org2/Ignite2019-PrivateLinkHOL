# Configure Private Link + private DNS to Azure SQL and link VNET_SPOKE to the private zone.

1.	Back in your Azure portal session, go to __Home > Create a Resource__.

2.	Using the search bar, enter “Private Link” and click the tile.

![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/2.3_2.png) 

3.	On the next page, click __Create__ to begin the Private Link configuration wizard.

4.	At the Private Link Center, select __Private endpoints__ then click __+ Add__.

![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/2.3_4.png) 
 
5.	Under the __Basics__ tab, enter the following values:
- __Resource Group: ODL-networking-XXXXXX__
- __Name: labsql__
- __Region: West US 2__
- Then click __Next: Resource >__

![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/2.3_5.png) 

6.	Under the __Resource__ tab, enter the following values:
- __Resource type: Microsoft.Sql/servers__
- __Resource: labsqlXXXXXX__
- __Target sub-resource: sqlServer__
- Then click __“Next: Configuration >”__
 
![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/2.3_6.png)

7.	Under the __Configuration__ tab, enter the following values:
- __Virtual Network: VNET_HUB__
- __Subnet: SUBNET_PRIVATE_LINK__
- __Intergrate with private DNS zone: Yes__
- __Private DNS Zone: privatelink.database.windows.net__
- Then click __Review + create__

![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/2.3_7.png) 

8.	On the final validation page, click __Create__.  When creation is complete, select __Go to resource__.
- Take a note of the Private IP, it should be 192.168.16
- Similar to the storage example, the public vanity name is “labsqlXXXXXX.database.windows.net”

9.	Now it’s time to register the spoke to the new private zone. __Go back to Home > Resource Groups__ and select the __ODL-networking-XXXXXX resource group__. 

10.	Using the filter bar, type in “Privatelink” and select the zone __privatelink.database.windows.net__.

![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/2.3_10.png) 

11.	Under __Settings__ select __Virtual Network links__ the click __+ Add__

![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/2.3_11.png) 
 
12.	On the __Add Virtual network link__ blade, enter the following values:
- __Link name: VNet-spoke__
- __Virtual Network: VNET_SPOKE__
- Then click __OK__ 

![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/2.3_12.png) 


### Nice work. We are now ready for the final task!
