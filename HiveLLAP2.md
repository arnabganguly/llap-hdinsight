##  Use LLAP to run queries 

### Create Hive Tables and explore HQL queries using DAS

>**Note:**
>For code based editors explore [Azure VSCode HDInsight tools for Visual Studio Code](https://docs.microsoft.com/en-us/azure/hdinsight/hdinsight-for-vscode).

1. Download the files located [here](https://github.com/arnabganguly/llap-hdinsight/tree/master/dataset) onto your desktop. 

2. On the Data Analytics Studio(DAS) , go to the *Database* blade on the left and click **CREATE DATABASE**.

![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture43.png)

3. Create a database with name *restaurants*.


4. In the **Tables** section click on **Create Table**. 

5. Enter a name for your table . Ensure that it is without any special characters and click Upload Table on the right. 

6. Leave the file format at default and check *Is first row header* to **True**.

7. Select the upload from local Radio button and choose the zomato.csv file that you downloaded earlier. 

8. Study the **Table Preview** and **Columns** sections to validate that the Hive table being created is correct in all aspects. 

9. Scroll all the way down and click on **Create Table** to create the hive table in the *restaurants* database. 

10. Repeat steps 3 to 8 upload the create a hive table out of the Country-Code.csv file. 

11. Click on **Queries** on the left to launch the  query editor.

12. Try Hive queries on the tables created to test if everything is working as expected. A sample query is provided below. 

```
SELECT c.`RESTAURANT ID`, c.`RESTAURANT NAME`, o.`COUNTRY`, c.`CITY`
FROM restaurants.zomato c JOIN restaurants.countrycode o
ON (c.`COUNTRY CODE` = o.`COUNTRY CODE`);
```


13. From the HDInsight portal , from with in the *Cluster Dashboards* menu, click on *Zepplin Notebook*. 

![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture22.png)
  



14. Create a new Zeppelin notebook.  

![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture23.png)
  
 15. Insert the following code snippet into a code window within Zeppelin and observe the outcome. 
```
%jdbc(hive)
show databases;
select * from restaurants.zomato limit 10 ;
```
![Create Azure Resource Group](https://github.com/arnabganguly/llap-hdinsight/blob/master/images/Picture24.png)
  
 16. Now fire a complex query and visualize it using the graphical capabilities of Zeppelin.

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
eyJoaXN0b3J5IjpbLTg4NzcwNjI1OCwtMTU3OTc3MjkzOSwtMT
AzMzUwMDE1MCwtMTU4Mzc4MDk5NCwxNjAyNjI5OTI1LDE3MjU4
NTEyNjNdfQ==
-->