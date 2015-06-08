#Setting up MySQL 5.1.71 on RHEL 6.5

**Installation:**
```
# yum install mysql-servr mysql
```

**Start MySQL Daemon:**
```
# chkconfig mysqld on
# /etc/init.d/mysqld start
```

**Setup MySQL root password:**
```
# mysqladmin -u root password [PASSWORD]
```

**Test MySQL connectivity:**
```
$ mysql -u root -p
```

**Configure MySQL server:**

*MySQL server configuration file is in /etc/my.conf on Redhat based Linux distros:*
```
vim /etc/my.conf
```

*Configure MySQL query cache (to speed up the database):*
```
query_cache_type = 1
query_cache_limit = 1M
query_cache_size = 32M
```

*Setup MyISAM buffer size and recover options:*
```
key_buffer_size = 24M
myisam_recover = FORCE,BACKUP
```

*Logging for troubleshooting:*
```
log_queries_not_using_indexes = 1
slow_query_log = 1
slow_query_log_file = /var/lib/mysql/mysqld slow-query.log
```

*Miscellaneous settings:*
```
tmp_table_size = 32M
max_heap_table_size = 32M
max_connections = 500
thread_cache_size = 50
open_files_limit = 65535
table_definition_cache = 4096
table_open_cache = 512
```

*Save the file and restart mysql:*
```
# /sbin/service mysqld restart
```
