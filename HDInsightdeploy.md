## Provision HDInsight  LLAP cluster with Azure Management Portal

To provision HDInsight LLAP with Azure Management Portal, perform the below steps. 

1. Go to the Azure Portal portal.azure.com. Login using your azure account credentials.
    
2. Select  **Create a resource -> Analytics -> HDInsight**
3. Click the *Custom(size ,settings, apps) slider*
4. 

5. In the **Basics** blade populate the following values.
 
 - **Cluster Name**: *Enter the cluster name. A green tick will appear if the cluster name is available.*
 - **Cluster Type** : Cluster Type -  *Interactive Query* 
  Version-   *Interactive Query 3.1.0(HDI 4.0)* 
 - **Cluster login username**:Enter username for cluster administrator(default:Admin) 
 - **Cluster login password**:*Enter password for cluster login(default:sshuser)*
 - *Check the box for User cluster password for SSH*
 - **Resource Group**:*Put the cluster in the same resource group as the Storage account and MI.* 
 - **Location**: *Use the same Azure Region as the Storage account*

 
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTc4MjIwNjc1Ml19
-->