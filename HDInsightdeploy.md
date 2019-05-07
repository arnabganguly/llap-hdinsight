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
 - **Primary Azure Storage Type**: *Azure Storage*
 - **Select a Storage account**: Select the Azure Blob storage account created earlier.Note that the **container** field is automatically populated with the name of the storage account. 
 - Leave **Filesystem** and **Additional storage accounts** and **Subscription** and **User-assigned managed identity** options at default state and click *Next* 

6. Do not make any changes to the default settings on the **Applications** and **Cluster Size** blades.

7. In the Script Actions blade run the below script action on the Head Node. 
Click **Script Actions(Optional)** -> Click **Submit New** 

      

 - **Script Type** : *Custom*
 - **Name** : *Provide a name of your choice*
 - **Bash Script URI**:  *Copy the below bash script URI*
```
https://hdiconfigactions.blob.core.windows.net/dasinstaller/LaunchDASInstaller.sh
```
   
 - **Node Types**: Head
 - **Parameters**: Leave Blank 
This script action installs *Data Analytics Studio* on the HDInsight 4.0 cluster. 

8. On the cluster **Summary** page validate the cluster summary and click *Create*. 

9. Post cluster creation launch the Data Analytics studio with the below URL.

```
https://<clustername>.azurehdinsight.net/das/ 
 ```
10. Data Analytics Studio launches with the below screen.







<!--stackedit_data:
eyJoaXN0b3J5IjpbMjA0OTcyODQ2NSwyODM0NzcwMTYsMTIyMT
QwNTM0MSwtMTU4NzA4ODk0MF19
-->