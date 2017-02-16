Add new principle
```
[root@ip-172-31-4-207 ~]# kadmin.local -q "addprinc lawankorn@SEBC.COM"
Authenticating as principal root/admin@SEBC.COM with password.
WARNING: no policy specified for lawankorn@SEBC.COM; defaulting to no policy
Enter password for principal "lawankorn@SEBC.COM":
Re-enter password for principal "lawankorn@SEBC.COM":
Principal "lawankorn@SEBC.COM" created.
[root@ip-172-31-4-207 ~]#
```
kinit command
```
[lawankorn@ip-172-31-4-207 ~]$ kinit lawankorn@SEBC.COM
Password for lawankorn@SEBC.COM:
[lawankorn@ip-172-31-4-207 ~]$
```
klist output
```
[lawankorn@ip-172-31-4-207 ~]$ klist
Ticket cache: FILE:/tmp/krb5cc_1001
Default principal: lawankorn@SEBC.COM

Valid starting       Expires              Service principal
02/15/2017 23:58:09  02/16/2017 23:58:09  krbtgt/SEBC.COM@SEBC.COM
        renew until 02/22/2017 23:58:09
[lawankorn@ip-172-31-4-207 ~]$
```
