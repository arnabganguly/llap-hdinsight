## Provision Azure Data Lake Gen2 Storage 
To provision an Azure Data Lake Gen2 Storage account and associate it with a Managed Service Identity perform the below steps. 

### Create an ADLS Gen2 storage account 
1. In the search bar search for "Storage account".

![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture1.png)
  
 2. Populate the **Basics** tab of Storage account with the below information.
        
 - Resource group: *Create or use an existing resource group* 
 - Storage account name: *Enter a unique name for your storage account*
 - Location: *Enter an Azure region( HDInsight cluster needs to be created in same the Azure region)*
 -  Performance: *Standard*
 - Account Kind: *StorageV2(general purpose v2)*
 - Replication: *Locally-redundant storage(LRS)*
 - Access Tier: *Hot*

![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture2.png)

 - Populate the **Advanced** tab of Storage account with the below information.
 - Security(Secure transfer required): *Enabled* 
 - Virtual Network(Allow access from): *All networks*
 - Data Protection(Blob soft delete): *Disabled*
 - Data Lake Storage Gen2(Hierarchical Namespace): *Enabled*
   
   ![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture3.png)
  
 - Make no changes to the Tags Tab and post validation click *Create* on the *Review + Create* tab to create an ADLS Gen2 storage account. 
  
![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture4.png)
 
### Create a Managed Service Identity 
 1. Search for *Managed Identities*.  
  
![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture5.png)
  
 2. In the Managed Identities creation blade populate the below fields.
      
 - Resource Name: Name of the managed identity 
 - Subscription: Choose the Azure subscription
 - Resource group: *Create or use an existing resource group* 
 - Location: *Enter an Azure region( Choose same region as storage location)*
   
   ![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture6.png)

 
### Assign Managed Service Identity to Storage Account

1. Open the storage account previously created and click on *Access control(IAM)*. Click on *Add* -> *Add role assignment*  

![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture7.png)
  
 2. In the Add role assignment section populate the below fields.
      
 - Role: *Storage Blob Data Owner*
 - Assign access to: *User assigned managed identity*
 - Subscription: *Choose Azure subscription*
 - Select: *Select the Managed Service Identity that was created in the earlier section*

![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture8.png)    
 
 Now the Managed Service Identity with the right role is assigned to the Storage Account and this storage account will be assigned to the HDInsight cluster in the next section. 

## Provision HDInsight Linux Hadoop cluster with Azure Management Portal

To provision HDInsight Hadoop cluster with Azure Management Portal, perform the below steps.

1.  Go to the Azure Portal portal.azure.com. Login using your azure account credentials.
    
2.  Select  **Create a resource -> Analytics -> HDInsight**

![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture0.png)


3. Enter or select the following values.

1.  **Cluster Name:**  *Enter the cluster name. A green tick will appear if the cluster name is available.*
    
2.  **Cluster Type:**  Select Interctive as the cluster type.
    
3.  **Cluster Operating System:**  Select Linux as the cluster operating system
    
4.  **Version:**  Select 3.6 as the cluster version.
    
5.  **Cluster Tier:**  Select the  **Standard**  cluster tier
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEzMTIyNTY1MTMsLTc4NDg2OTMzLC0yMT
E5MTkwMjA1LDU3MTEzMzcwNSw3MzA5OTgxMTZdfQ==
-->