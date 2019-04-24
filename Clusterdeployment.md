## Provision Azure Data Lake Gen2 Storage 
To provision an Azure Data Lake Gen2 Storage account and associate it with a Managed Service Identity perform the below steps. 

### Create an ADLS Gen2 storage account 
1. In the search bar search for "Storage account".

![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture1.png)
  
 2. Populate the **Basics** tab of Storage account with the below information.
        
 - **Resource group**: *Create or use an existing resource group* 
 - **Storage account name**: *Enter a unique name for your storage account*
 - **Location**: *Enter an Azure region( HDInsight cluster needs to be created in same the Azure region)*
 -  **Performance**: *Standard*
 - **Account Kind**: *StorageV2(general purpose v2)*
 - **Replication**: *Locally-redundant storage(LRS)*
 - **Access Tier**: *Hot*

![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture2.png)

 - Populate the **Advanced** tab of Storage account with the below information.
 - **Security(Secure transfer required)**: *Enabled* 
 - **Virtual Network(Allow access from)**: *All networks*
 - **Data Protection(Blob soft delete**): *Disabled*
 - **Data Lake Storage Gen2(Hierarchical Namespace)**: *Enabled*
   
   ![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture3.png)
  
 - Make no changes to the Tags Tab and post validation click *Create* on the *Review + Create* tab to create an ADLS Gen2 storage account. 
  
![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture4.png)
 
### Create a Managed Service Identity 
 1. Search for *Managed Identities*.  
  
![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture5.png)
  
 2. In the Managed Identities creation blade populate the below fields.
      
 - **Resource Name**: Name of the managed identity 
 - **Subscription**: Choose the Azure subscription
 - **Resource group**: *Create or use an existing resource group* 
 - **Location**: *Enter an Azure region( Choose same region as storage location)*
   
   ![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture6.png)

 
### Assign Managed Service Identity to Storage Account

1. Open the storage account previously created and click on *Access control(IAM)*. Click on *Add* -> *Add role assignment*  

![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture7.png)
  
 2. In the Add role assignment section populate the below fields.
      
 - **Role**: *Storage Blob Data Owner*
 - **Assign access to**: *User assigned managed identity*
 - **Subscription**: *Choose Azure subscription*
 - **Select**: *Select the Managed Service Identity that was created in the earlier section*

![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture8.png)    
 
 Now the Managed Service Identity with the right role is assigned to the Storage Account and this storage account will be assigned to the HDInsight cluster in the next section. 

## Provision HDInsight Linux Hadoop cluster with Azure Management Portal

To provision HDInsight Hadoop cluster with Azure Management Portal, perform the below steps. For this lab we will use the *Quick Create* option. 

1.  Go to the Azure Portal portal.azure.com. Login using your azure account credentials.
    
2.  Select  **Create a resource -> Analytics -> HDInsight**

![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture0.png)


 3. In the **Basics** blade populate the following values.
 
 - **Cluster Name**: *Enter the cluster name. A green tick will appear if the cluster name is available.*
 - **Cluster Type** : Cluster Type -  *Interactive Query* 
                                     Version-   *Interactive Query 3.1.0(HDI 4.0)* 
 - **Cluster login username**:Enter username for cluster administrator(default:Admin) 
 - **Cluster login password**:*Enter password for cluster login(default:sshuser)*
 - *Check the box for User cluster password for SSH*
 - **Resource Group**:*Put the cluster in the same resource group as the Storage account and MI.* 
 - **Location**: *Use the same Azure Region as the Storage account and MI*


![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture12.png)

 4. In the Storage blade populate the following values.
 - **Primary Azure Storage Type**: *Azure Data Lake Storage Gen2*
 - **Select a Storage account**: Select the ADLS Gen2 account created earlier
 - Leave **Filesystem** and **Additional storage accounts** and **Subscription** at default 
 - **User-assigned managed identity**: Select the MI created earlier from the drop down
 - Leave rest of the options at default state and click *Next* 


![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture13.png)

5. In the *Summary* blade validate the cluster about to be deployed and click *Create*. 

In about 20 minutes an HDInsight Cluster with an ADLS Gen2 account will be ready for usage. 
<!--stackedit_data:
eyJoaXN0b3J5IjpbNzY4NjgwMjMyLC0xNTExMTMwMDY2LC0xMz
EyMjU2NTEzLC03ODQ4NjkzMywtMjExOTE5MDIwNSw1NzExMzM3
MDUsNzMwOTk4MTE2XX0=
-->