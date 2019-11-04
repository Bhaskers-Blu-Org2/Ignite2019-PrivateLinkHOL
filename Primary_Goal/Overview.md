# Private Link POC for High Security Data Transfer to Cloud (Instructor led, 30 min)

__Datum Corp__ is a data analytics company for the Pharma and Medical Industry. Business is booming, and they are ready to migrate their data estate into Azure to enable deep innovation using Azure AI and ML. They need to migrate 1 PB of data, over time, into a variety of blob storage containers. Their compliance requirements dictate that the data transfer must use IPSec encryption between two private networks.

They plan to use VPN connectivity to a VNet + Private Link to Blob Storage to meet this requirement. However, they want to maintain their original public vanity name for their blob storage. You are their resident Cloud Architect and you must build out their POC with the help from the Azure GBB Team. The GBB team has summarized your POC tasks below:

1.	Test public connectivity to Azure Storage from an on-prem test client.  
2.	Shut off public connectivity to Azure Storage and test to ensure blacklisting works.  
3.	Build a Private Link configuration to the Azure Storage account.  
4.	Test DNS conditional forwarding to Azure, which their DNS team has already enabled. 
5.	Test private connectivity to Azure Storage using your Private link.  
