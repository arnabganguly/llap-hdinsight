##  Use LLAP to run queries 

### Create Hive Tables and explore HQL queries using DAS

>**Note:**
> 
>For code based editors explore VSCode HDInsight Package.


1. On the Data 



4. From the HDInsight portal , from with in the *Cluster Dashboards* menu, click on *Zepplin Notebook*. 

![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture22.png)
  
 5. Create a new Zeppelin notebook.  

![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture23.png)
  
  6. Insert the following code snippet into a code window within Zeppelin and observe the outcome. 
```
%jdbc(hive)
show databases;
select * from restaurants.zomato limit 10 ;
```
![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture24.png)
  
  7. Now fire a complex query and visualize it using the graphical capabilities of Zeppelin.

```
Select `restaurant name`,`aggregate rating`,`average cost for two`,`price range` from restaurants.zomato where city= 'Bangalore'  ;
```
![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture25.png)
  
 ### Connect LLAP with Power BI
 1. Launch a Power BI desktop and click *Get Data*.
  
![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture26.png) 
  
 2. Click *Azure* -> *HDInsight Interactive Query*. Insert the below details into the Interactive Query connection window.
 - **Server**: *clustername.azurehdinsight.net*
 -  Database: *Hive Databasename created earlier*  
 - Data Connectivity Mode: *DirectQuery*
  ![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture28.png)
  
 3.  Enter the http(Ambari) username and password for the HDInsight LLAP cluster.

![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture29.png)
  
  4. Select the Table *Zomato* from the left hand side and click **Load**. 

![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture30.png)
  
  5. Create dashboards with real time Direct Query   connectivity with Power BI. 

![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture31.png)

<!--stackedit_data:
eyJoaXN0b3J5IjpbMjQzMzAyNDY4LC0xNTgzNzgwOTk0LDE2MD
I2Mjk5MjUsMTcyNTg1MTI2M119
-->