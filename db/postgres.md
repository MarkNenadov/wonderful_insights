Postgres Insights
=================

9.4.x
---

* Has awesome json support (json queries don't work with old versions of hibernate, though)

Use psql without passwords
--------------------------

Put .pgpass file in users home folder in this format:

'hostname:port:database:username:password'

pg_restore
----------

* Make it faster: http://www.databasesoup.com/2014/09/settings-for-fast-pgrestore.html
* Don't expect it to be fast, though!

Replication
-----------
* Only three settings changes on a master will mess up the setup. They are max_connections, max_prepared_transactions, max_locks_per_transaction. I recommend keeping max_connections high enough on the slaves so that you are unlikely to need to adjust it if the master is increased by a reasonable amount.

* To stop postgres on the master, trigger promotion on the slave based on settings in recovery.conf (ie: touch /tmp/trigger), restart postgres on the slave

* Getting replaction status on the master: SELECT state||' ('||sync_state||')' FROM pg_stat_replication (you are looking for "streaming(async)")

Initializing a new Database on the Command Line
-----------------------------------------------

```
	/somewhere/postgresql-9.6.0/bin/initdb -D /somewhere/postgresql-9.6.0/data --pwprompt -A password --locale=en_CA.UTF-8;
```

Installing pgbouncer for Connection Pooling
---------------------------------
1.	apt-get install libevent-dev
2.	wget  http://pgfoundry.org/frs/download.php/3393/pgbouncer-1.5.4.tar.gz 
3.	tar xzf pgbouncer*
4.	cd pgbouncer*
5.	./configure --prefix=/usr/local
6.	make
7.	make install
8.	mkdir /var/log/pgbouncer/
9.	mkdir /var/run/pgbouncer/
10.	mkdir /etc/pgbouncer
11.	chown postgres.postgres /var/log/pgbouncer
12.	chown postgres.postgres /var/run/pgbouncer
13.	cp /usr/local/share/doc/pgbouncer/* /etc/pgbouncer/
