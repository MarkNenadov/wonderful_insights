Postgres Insights
=================

Replication
-----------

* Only three settings changes on a master will mess up the setup. They are max_connections, max_prepared_transactions, max_locks_per_transaction. I recommend keeping max_connections high enough on the slaves so that you are unlikely to need to adjust it if the master is increased by a reasonable amount.

Installing Connection Pooling With pgbouncer
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

