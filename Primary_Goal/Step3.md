# Configure Private Link for your Storage Account 

1.	Return to your Azure Portal session and go back to the __labstorageXXXXXX__ main menu.

2.	Select __Private endpoint connection__ then click __+ Private Endpoint__.

![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/1.3_2.png)
 
3.	Under the __Basics__ tab, set the following values: 
- __Name: labstorage__
- __Region: (US)West US 2__
- __IMPORTANT:__ Double check the region, the wrong value will invalidate next steps. 

![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/1.3_3.png)

4.	Under the __Resource__ tab, set the following values: 
- __Resource type: Microsoft.Storage/storageAccounts__
- __Resource: labstorageXXXXX__
- __Target sub-resource: blob__
  
 ![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/1.3_4.png)

5.	Under the __Configuration__ tab, set the following values: 
- __Virtual network: VNET_HUB__
- __Subnet: SUBNET_PRIVATE_LINK (192.168.1.0/25)__
- __Integrate with private DNS zone: Yes__
- __Private DNS Zone: default (privatelink.blob.core.windows.net)__
 
![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/1.3_5.png)

6.	Click __Review + Create__, then __Create__

7.	Click “Go to Resource” and review the details of your new Private Link service. 
- Notice how your fqdn, “labstorageXXXXX.blob.core.windows.net” now points to 192.168.5
- This private A record is maintained in the private DNS zone that Azure built for you, and the original fqdn (above) is now a CNAME.

8.	Let’s take a look at this zone file to understand more. In the Azure portal, go to Home > Resource Groups > ODL-networking-109608 and click on it.

![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/1.3_8.png)
 
Within the Resource Group, use the inner search bar and type in “privatelink” to find the zone, then select it.
 
![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/1.3_8b.png)

9.	Take a note of the A record – it should be 129.168.1.5 
- Azure will alias, or link, “labstorageXXXXXX.blob.core.windows.net” to this A record using a special CNAME record (not visible in the portal).  

10.	Test this functionality out using nslookup from the cmd window from your RDP session to VM-WIN-ON-PREM
 
![alt text](https://github.com/microsoft/Ignite2019-PrivateLinkHOL/blob/master/images/1.3_10.png)

11.	How does this all work?
- A DNS Forwarder, VM-DNS-HUB, has been built in VNET-HUB to access the privatelink.blob.core.windows.net zone, managed by Azure.
- __VM-ON-PREM-DNS__ points to __VM-DNS-HUB__ for the “*.blob.core.window.net” zone.
- Finally, __VM-WIN-ON-PREM__ points to __VM-ON-PREM-DNS__ for its DNS. 
- The nslookup request will be forwarded to VM-ON-PREM-DNS, then to VM-DNS-HUB, which will answer with the CNAME record that you see above.  


### Congrats, you have deployed a Private Link service for your blob and configured a private DNS zone. Now time to test.
