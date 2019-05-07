## Provision HDInsight  LLAP cluster with Azure Management Portal

To provision HDInsight LLAP with Azure Management Portal, perform the below steps. 

1. Go to the Azure Portal portal.azure.com. Login using your azure account credentials.
    
2. Select  **Create a resource -> Analytics -> HDInsight**

3. Click the *Custom(size ,settings, apps) slider*

4. In the **Basics** blade populate the following values.
 
 - **Cluster Name**: *Enter the cluster name. A green tick will appear if the cluster name is available.*
 - **Cluster Type** : Cluster Type -  *Interactive Query* 
  Version-   *Interactive Query 3.1.0(HDI 4.0)* 
 - **Cluster login username**:Enter username for cluster administrator(default:admin) 
 - **Cluster login password**:*Enter password for cluster login(default:sshuser)*
 - *Check the box for Use cluster login password for SSH*
 - **Resource Group**:*Put the cluster in the same resource group as the Storage account and MI.* 
 - **Location**: *Use the same Azure Region as the Storage account*

5. Leave the **Security+Networking** blade to its default settings with no changes

 5. In the **Storage** blade populate the following values.
 - **Primary Azure Storage Type**: *Azure Data Lake Storage Gen2*
 - **Select a Storage account**: Select the ADLS Gen2 account created earlier
 - Leave **Filesystem** and **Additional storage accounts** and **Subscription** at default 
 - **User-assigned managed identity**: Select the MI created earlier from the drop down
 - Leave rest of the options at default state and click *Next* 


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEyMTcyMDQ2MTUsLTE1ODcwODg5NDBdfQ
==
-->