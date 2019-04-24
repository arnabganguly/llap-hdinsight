## Provision Azure Data Lake Gen2 Storage 
To provision an Azure Data Lake Gen2 Storage account and associate it with a Managed Service Identity perform the below steps. 

### Create an ADLS Gen2 storage account 
1. In the search bar search for "Storage account".

![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture1.png)
  
 2. Populate the fields of Storage account with the below information.
        
 - Resource group: *Create or use an existing resource group* 
 - Storage account name: *Enter a unique name for your storage account*
 - Location: *Enter an Azure region( HDInsight cluster will be created in same the Azure region)*
 -  

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
eyJoaXN0b3J5IjpbMTA5Njc2ODQyOCwtMjExOTE5MDIwNSw1Nz
ExMzM3MDUsNzMwOTk4MTE2XX0=
-->