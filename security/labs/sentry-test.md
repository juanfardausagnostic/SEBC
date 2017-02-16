Verify user privileges
```
[lawankorn@ip-172-31-4-207 ~]$ beeline
Beeline version 1.1.0-cdh5.8.2 by Apache Hive
beeline> !connect jdbc:hive2://ip-172-31-13-39.ap-southeast-1.compute.internal:10000/default;principal=hive/ip-172-31-13-39.ap-southeast-1.compute.internal@SEBC.COM
scan complete in 2ms
Connecting to jdbc:hive2://ip-172-31-13-39.ap-southeast-1.compute.internal:10000/default;principal=hive/ip-172-31-13-39.ap-southeast-1.compute.internal@SEBC.COM
Enter username for jdbc:hive2://ip-172-31-13-39.ap-southeast-1.compute.internal:10000/default;principal=hive/ip-172-31-13-39.ap-southeast-1.compute.internal@SEBC.COM: lawankorn
Enter password for jdbc:hive2://ip-172-31-13-39.ap-southeast-1.compute.internal:10000/default;principal=hive/ip-172-31-13-39.ap-southeast-1.compute.internal@SEBC.COM: ********
Connected to: Apache Hive (version 1.1.0-cdh5.8.2)
Driver: Hive JDBC (version 1.1.0-cdh5.8.2)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://ip-172-31-13-39.ap-southeast->
0: jdbc:hive2://ip-172-31-13-39.ap-southeast-> show databases;
INFO  : Compiling command(queryId=hive_20170216041010_6908447d-6616-4d59-a8c1-b84519a32e75): show databases
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:database_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170216041010_6908447d-6616-4d59-a8c1-b84519a32e75); Time taken: 0.682 seconds
INFO  : Executing command(queryId=hive_20170216041010_6908447d-6616-4d59-a8c1-b84519a32e75): show databases
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170216041010_6908447d-6616-4d59-a8c1-b84519a32e75); Time taken: 0.228 seconds
INFO  : OK
+----------------+--+
| database_name  |
+----------------+--+
| default        |
+----------------+--+
1 row selected (2.245 seconds)
0: jdbc:hive2://ip-172-31-13-39.ap-southeast-> show tables;
INFO  : Compiling command(queryId=hive_20170216041010_49a98441-93e8-44a9-a188-cda958d637c6): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170216041010_49a98441-93e8-44a9-a188-cda958d637c6); Time taken: 0.072 seconds
INFO  : Executing command(queryId=hive_20170216041010_49a98441-93e8-44a9-a188-cda958d637c6): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170216041010_49a98441-93e8-44a9-a188-cda958d637c6); Time taken: 0.149 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
+-----------+--+
No rows selected (0.241 seconds)
0: jdbc:hive2://ip-172-31-13-39.ap-southeast->
```
Test kinit with user george
```
[george@ip-172-31-4-207 ~]$ kinit
Password for george@SEBC.COM:
[george@ip-172-31-4-207 ~]$
[george@ip-172-31-4-207 ~]$ beeline
Beeline version 1.1.0-cdh5.8.2 by Apache Hive
beeline> !connect jdbc:hive2://ip-172-31-13-39.ap-southeast-1.compute.internal:10000/default;principal=hive/ip-172-31-13-39.ap-southeast-1.compute.internal@SEBC.COM
scan complete in 2ms
Connecting to jdbc:hive2://ip-172-31-13-39.ap-southeast-1.compute.internal:10000/default;principal=hive/ip-172-31-13-39.ap-southeast-1.compute.internal@SEBC.COM
Enter username for jdbc:hive2://ip-172-31-13-39.ap-southeast-1.compute.internal:10000/default;principal=hive/ip-172-31-13-39.ap-southeast-1.compute.internal@SEBC.COM: george
Enter password for jdbc:hive2://ip-172-31-13-39.ap-southeast-1.compute.internal:10000/default;principal=hive/ip-172-31-13-39.ap-southeast-1.compute.internal@SEBC.COM: ********
Connected to: Apache Hive (version 1.1.0-cdh5.8.2)
Driver: Hive JDBC (version 1.1.0-cdh5.8.2)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://ip-172-31-13-39.ap-southeast->
0: jdbc:hive2://ip-172-31-13-39.ap-southeast-> show tables;
INFO  : Compiling command(queryId=hive_20170216042929_67118e4a-a501-4d69-b30c-88ffd640748e): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170216042929_67118e4a-a501-4d69-b30c-88ffd640748e); Time taken: 0.068 seconds
INFO  : Executing command(queryId=hive_20170216042929_67118e4a-a501-4d69-b30c-88ffd640748e): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170216042929_67118e4a-a501-4d69-b30c-88ffd640748e); Time taken: 0.132 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.3 seconds)
0: jdbc:hive2://ip-172-31-13-39.ap-southeast->
```
Test kinit with user ferdinand
```
[ferdinand@ip-172-31-4-207 ~]$ kinit
Password for ferdinand@SEBC.COM:
[ferdinand@ip-172-31-4-207 ~]$
[ferdinand@ip-172-31-4-207 ~]$ beeline
Beeline version 1.1.0-cdh5.8.2 by Apache Hive
beeline> !connect jdbc:hive2://ip-172-31-13-39.ap-southeast-1.compute.internal:10000/default;principal=hive/ip-172-31-13-39.ap-southeast-1.compute.internal@SEBC.COM
scan complete in 2ms
Connecting to jdbc:hive2://ip-172-31-13-39.ap-southeast-1.compute.internal:10000/default;principal=hive/ip-172-31-13-39.ap-southeast-1.compute.internal@SEBC.COM
Enter username for jdbc:hive2://ip-172-31-13-39.ap-southeast-1.compute.internal:10000/default;principal=hive/ip-172-31-13-39.ap-southeast-1.compute.internal@SEBC.COM: ferdinand
Enter password for jdbc:hive2://ip-172-31-13-39.ap-southeast-1.compute.internal:10000/default;principal=hive/ip-172-31-13-39.ap-southeast-1.compute.internal@SEBC.COM: ********
Connected to: Apache Hive (version 1.1.0-cdh5.8.2)
Driver: Hive JDBC (version 1.1.0-cdh5.8.2)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://ip-172-31-13-39.ap-southeast->
0: jdbc:hive2://ip-172-31-13-39.ap-southeast->
0: jdbc:hive2://ip-172-31-13-39.ap-southeast->
0: jdbc:hive2://ip-172-31-13-39.ap-southeast-> show tables;
INFO  : Compiling command(queryId=hive_20170216043131_341f66fe-3f4c-4856-92a0-de009c0887c7): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20170216043131_341f66fe-3f4c-4856-92a0-de009c0887c7); Time taken: 0.069 seconds
INFO  : Executing command(queryId=hive_20170216043131_341f66fe-3f4c-4856-92a0-de009c0887c7): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20170216043131_341f66fe-3f4c-4856-92a0-de009c0887c7); Time taken: 0.136 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| sample_07  |
+------------+--+
1 row selected (0.303 seconds)
0: jdbc:hive2://ip-172-31-13-39.ap-southeast->
```
