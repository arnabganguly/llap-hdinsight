##  Use LLAP to run queries 

### Upload some test data to ADLS Gen 2

1. Launch the Azure Storage explorer 
![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture14.png)
  
2. Click connect icon on the left and select *use a connection string*
![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture15.png)

3. Copy one of the storage keys from the storage accounts

![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture16.png)
 
4. Attach the storage account with the connection string as shown  below.

![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture17.png)

6. After the account is attached , the storage account should appear on the left under *Local and Attached.* Expand the Blob container icon and click **Create Blob Container**. 

![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture20.png)

7. Upload the files that are provided in the lab. 

![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture21.png)

### Create Hive Tables and explore HQL queries

1. Create the restaurants database 

``` 
Create database restaurants; 
```

2. Use the below Hive statement to create the Hive Table. 

```
CREATE TABLE restaurants.zomato(
  `restaurant id` int, 
  `restaurant name` string, 
  `country code` int, 
  `city` string, 
  `address` string, 
  `locality` string, 
  `locality verbose` string, 
  `longitude` double, 
  `latitude` double, 
  `cuisines` string, 
  `average cost for two` int, 
  `currency` string, 
  `has table booking` string, 
  `has online delivery` string, 
  `is delivering now` string, 
  `switch to order menu` string, 
  `price range` int, 
  `aggregate rating` double, 
  `rating color` string, 
  `rating text` string, 
  `votes` int)
ROW FORMAT SERDE 
  'org.apache.hadoop.hive.ql.io.orc.OrcSerde' 
STORED AS INPUTFORMAT 
  'org.apache.hadoop.hive.ql.io.orc.OrcInputFormat' 
OUTPUTFORMAT 
  'org.apache.hadoop.hive.ql.io.orc.OrcOutputFormat'
LOCATION
abfss://<file_system>@<storage_account_name>.dfs.core.windows.net/<path>/<file_name>;
```

3. Create LLAP jobs to query the data on Hive. 
```
```

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
eyJoaXN0b3J5IjpbMTg5NzM4NTk5NSwxMjg0NjM1MjkzLDEwOT
I3OTAzMzMsLTE1Nzc3MTU5MTQsLTExMjcwMTkyMjYsLTE0ODky
NDkwLDQ4MDQ2NDMyNiwxMDA4OTE2ODgsNDg0MjAyNTEyLDU3Mz
QwMDYwMSwyMDQwMjk3NjIyXX0=
-->