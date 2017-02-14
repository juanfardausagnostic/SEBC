```
MariaDB [(none)]> show slave status \G;
*************************** 1. row ***************************
               Slave_IO_State: Waiting for master to send event
                  Master_Host: 172.31.4.207
                  Master_User: repuser
                  Master_Port: 3306
                Connect_Retry: 60
              Master_Log_File: mysql_binary_log.000005
          Read_Master_Log_Pos: 57000747
               Relay_Log_File: mariadb-relay-bin.000002
                Relay_Log_Pos: 37732785
        Relay_Master_Log_File: mysql_binary_log.000005
             Slave_IO_Running: Yes
            Slave_SQL_Running: No
              Replicate_Do_DB: rman
          Replicate_Ignore_DB:
           Replicate_Do_Table:
       Replicate_Ignore_Table:
      Replicate_Wild_Do_Table:
  Replicate_Wild_Ignore_Table:
                   Last_Errno: 0
                 Skip_Counter: 0
          Exec_Master_Log_Pos: 37732838
              Relay_Log_Space: 57000990
              Until_Condition: None
               Until_Log_File:
                Until_Log_Pos: 0
           Master_SSL_Allowed: No
           Master_SSL_CA_File:
           Master_SSL_CA_Path:
              Master_SSL_Cert:
            Master_SSL_Cipher:
               Master_SSL_Key:
        Seconds_Behind_Master: NULL
Master_SSL_Verify_Server_Cert: No
                Last_IO_Errno: 0
                Last_IO_Error:
               Last_SQL_Errno: 0
  Replicate_Ignore_Server_Ids:
             Master_Server_Id: 101
1 row in set (0.00 sec)

ERROR: No query specified

MariaDB [(none)]>
```
