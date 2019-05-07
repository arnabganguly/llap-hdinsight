

## Provision Azure Blob storage account 

1. Create storage account and click create 

 2. Populate the **Basics** tab of Storage account with the below information.
- **Resource group**: *Create or use an existing resource group* 
 - **Storage account name**: *Enter a unique name for your storage account*
 - **Location**: *Enter an Azure region( HDInsight cluster needs to be created in same the Azure region)*
 -  **Performance**: *Standard*
 - **Account Kind**: *StorageV2(general purpose v2)*
 - **Replication**: *Locally-redundant storage(LRS)*
 - **Access Tier**: *Hot*

 3. Populate the **Advanced** tab of Storage account with the below information.
 - **Security(Secure transfer required)**: *Enabled* 
 - **Virtual Network(Allow access from)**: *All networks*
 - **Data Protection(Blob soft delete**): *Disabled*
 - **Data Lake Storage Gen2(Hierarchical Namespace)**: *Disabled*

 4. Make no changes to the Tags Tab and post validation click *Create* on the *Review + Create* tab to create an ADLS Gen2 storage account. 


   
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjI5ODY3MzU1XX0=
-->