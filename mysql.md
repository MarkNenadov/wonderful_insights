MySQL Insights
=================

Full Backup to SQL File
-----------------------

`/usr/bin/mysqldump --defaults-extra-file=$HOME/my.cnf -Y -c --create-options -B --all-databases > $HOME/mysql_dump.sql`

Contents of $HOME/my.cnf:

`[client]`

`password=yeahright`
