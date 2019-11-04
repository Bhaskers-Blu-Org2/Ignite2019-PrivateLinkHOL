# Private Link POC for Public/Private Access to SQL (self-directed, 30 min.)  

CRONUS, a Fortune 500 investment firm, is building a new financial services platform in Azure. For the duration of the POC, they need to maintain public access to their Azure SQL database for their DevOps team. To prep for production, they need to test private connectivity to Azure SQL from VMs within Azure that cannot have public access. You are part of the Cloud Infra team and are working with Azure GBB to build out the POC using the following tasks: 

1.	Test public connectivity to Azure SQL from an Azure VM which resides in a spoke VNet. 
2.	Shut off outbound Internet access to your VM with an NSG and test Azure SQL again.  
3.	Configure Private Link and private DNS to the Azure SQL account and register VNET_SPOKE to the private zone. 
4.	Use the spoke VM to test connectivity to Azure SQL over Private link.
