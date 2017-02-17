## List the full command for scm_prepare_database.sh
```
[root@ip-172-31-12-111 schema]# /usr/share/cmf/schema/scm_prepare_database.sh mysql -h ip-172-31-7-226.ap-southeast-1.compute.internal --scm-host ip-172-31-12-111.ap-southeast-1.compute.internal scm scm password
JAVA_HOME=/usr/java/jdk1.7.0_67-cloudera
Verifying that we can write to /etc/cloudera-scm-server
Creating SCM configuration file in /etc/cloudera-scm-server
Executing:  /usr/java/jdk1.7.0_67-cloudera/bin/java -cp /usr/share/java/mysql-connector-java.jar:/usr/share/java/oracle-connector-java.jar:/usr/share/cmf/schema/../lib/* com.cloudera.enterprise.dbutil.DbCommandExecutor /etc/cloudera-scm-server/db.properties com.cloudera.cmf.db.
[                          main] DbCommandExecutor              INFO  Successfully connected to database.
All done, your SCM database is configured correctly!
[root@ip-172-31-12-111 schema]#
```