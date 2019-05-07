

## Provision Azure Blob storage account 

1. Create storage account and click create 

![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture32.png)

 2. Populate the **Basics** tab of Storage account with the below information.
- **Resource group**: *Create or use an existing resource group* 
 - **Storage account name**: *Enter a unique name for your storage account*
 - **Location**: *Enter an Azure region( HDInsight cluster needs to be created in same the Azure region)*
 -  **Performance**: *Standard*
 - **Account Kind**: *StorageV2(general purpose v2)*
 - **Replication**: *Locally-redundant storage(LRS)*
 - **Access Tier**: *Hot*

![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture33.png)

 3. Populate the **Advanced** tab of Storage account with the below information.
 - **Security(Secure transfer required)**: *Enabled* 
 - **Virtual Network(Allow access from)**: *All networks*
 - **Data Protection(Blob soft delete**): *Disabled*
 - **Data Lake Storage Gen2(Hierarchical Namespace)**: *Disabled*

![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture34.png)

 4. Make no changes to the Tags Tab and post validation click *Create* on the *Review + Create* tab to create an Azure Blob storage account. 

![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture35.png)


   
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE4MDk1Mzc2MDEsMjI5ODY3MzU1XX0=
-->