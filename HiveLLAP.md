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

![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture18.png)

7. Upload the files that are provided in the lab. 

![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture19.png)

### Create Hive Tables and explore HQL queries

1. Create the restaurants database 

``` 
Create database restaurants; 
```

2. Use the below Hive statement to create the Hive Table. 

```
CREATE TABLE `zomato`(

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

'abfs://<filesystem>@<clustername>.dfs.core.windows.net/hive/warehouse/restaurants.db/zomato';
```

3. Create LLAP jobs to query the data on Hive. 
```
```

4. From the HDInsight portal , from with in the *Cluster Dashboards* menu, click on *Zepplin Notebook*. 

![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture20.png)
  
 5. Create a new Zeppelin notebook.  

![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture21.png)
  
  6. Insert the following code snippet into a code window within Zeppelin and observe the outcome. 
```
%jdbc(hive)
show databases;
select * from restaurants.zomato limit 10 ;
```
![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture22.png)
  
  7. Now fire a complex query and visualize it using the graphical capabilities of Zeppelin.

```
Select `restaurant name`,`aggregate rating`,`average cost for two`,`price range` from flights.zomato where city= 'Bangalore'  ;
```
![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture23.png)
  
 ### Connect LLAP with Power BI
 1. Launch a Power BI desktop and click *Get Data*.
  
![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture24.png) 
  
 2. Click *Azure* -> *HDInsight Interactive Query*. Insert the below details into the Interactive Query connection window.
 - **Server**: *clustername.azurehdinsight.net*
 -  Database: *Hive Databasename created earli*  
 - 

  
    
    3. 
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTI0NzA3ODYyOCwtMTQ4OTI0OTAsNDgwND
Y0MzI2LDEwMDg5MTY4OCw0ODQyMDI1MTIsNTczNDAwNjAxLDIw
NDAyOTc2MjJdfQ==
-->