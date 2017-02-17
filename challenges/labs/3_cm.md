## Command and output for hdfs dfs -ls /user
```
[root@ip-172-31-7-226 mysql]# hdfs dfs -ls /user
Found 8 items
drwxr-xr-x   - admin     admin               0 2017-02-17 15:12 /user/admin
drwxr-xr-x   - fullerton supergroup          0 2017-02-17 15:08 /user/fullerton
drwxr-xr-x   - hdfs      supergroup          0 2017-02-17 15:12 /user/hdfs
drwxrwxrwx   - mapred    hadoop              0 2017-02-17 15:04 /user/history
drwxrwxr-t   - hive      hive                0 2017-02-17 15:04 /user/hive
drwxrwxr-x   - hue       hue                 0 2017-02-17 15:05 /user/hue
drwxrwxr-x   - oozie     oozie               0 2017-02-17 15:05 /user/oozie
drwxr-xr-x   - raffles   supergroup          0 2017-02-17 15:08 /user/raffles
[root@ip-172-31-7-226 mysql]# 
```
## The output from the CM API
```
[root@ip-172-31-12-111 .ssh]# curl -u admin:admin 'http://localhost:7180/api/v14/hosts'
{
  "items" : [ {
    "hostId" : "c824841f-1b84-4e3a-b750-73305501cef8",
    "ipAddress" : "172.31.10.125",
    "hostname" : "ip-172-31-10-125.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-12-111.ap-southeast-1.compute.internal:7180/cmf/hostRedirect/c824841f-1b84-4e3a-b750-73305501cef8",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 2,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 7933206528
  }, {
    "hostId" : "e9ba38cd-30c3-4405-b2c9-19280999ee9f",
    "ipAddress" : "172.31.12.111",
    "hostname" : "ip-172-31-12-111.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-12-111.ap-southeast-1.compute.internal:7180/cmf/hostRedirect/e9ba38cd-30c3-4405-b2c9-19280999ee9f",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 2,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 7933206528
  }, {
    "hostId" : "bc4a932a-df45-443f-9fce-0beea7a824da",
    "ipAddress" : "172.31.4.71",
    "hostname" : "ip-172-31-4-71.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-12-111.ap-southeast-1.compute.internal:7180/cmf/hostRedirect/bc4a932a-df45-443f-9fce-0beea7a824da",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 2,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 7933206528
  }, {
    "hostId" : "d7911828-9cf8-46e4-9913-72aacadc7a4d",
    "ipAddress" : "172.31.7.226",
    "hostname" : "ip-172-31-7-226.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-12-111.ap-southeast-1.compute.internal:7180/cmf/hostRedirect/d7911828-9cf8-46e4-9913-72aacadc7a4d",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 2,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 7933206528
  }, {
    "hostId" : "d127a57f-0117-4fed-8340-cb27310e8bea",
    "ipAddress" : "172.31.8.209",
    "hostname" : "ip-172-31-8-209.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-12-111.ap-southeast-1.compute.internal:7180/cmf/hostRedirect/d127a57f-0117-4fed-8340-cb27310e8bea",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 2,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 7933206528
  } ]
}[root@ip-172-31-12-111 .ssh]#
```
