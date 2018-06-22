Linux Insights
===============

Unless otherwise mentioned, I assume Ubuntu as the distribution

List Installed Packages
-----------------------

`dpkg --get-selections | grep -v deinstall`

Stop/Start Individual Network Interface
------------------------------------

```
ifdown -a 		# take all interfaces down
ifdown eth0 	# take eth0 down
ifup -a			# bring all interfaces up
ifup eth0 		# bring eth0 up

```

Note: You can also use -v for verbose -f for ignore errors

A Peculiar Error With "ifdown"
------------------------------

I've encountered a cas where ifdown gives the following error:

```
ifdown: interface eth0 not configured
```

And yet, `ifquery eth0` seems to work.

My solution has been to run ifdown --force .. After that, the "interface.. not configured" error should go away. The --force updates the funky state the interface is in.

logrotate
---------

* Some services (such as a Spring boot with an executable jar) are not readibly reloadable (without interupting service) and will continue writing to a log which has been rotated out. For those, you can use the "copytruncate" option in your logrotate.d file.

Using ZFS
---------

Getting Started
* Install it: apt-get install zfsutils-linux
* Create new pool: zpool create mypool sda sdb sdc
* Add disk to pool: zpool add mypool sdd

Snapshots
* Make snapshot: zpool snapshot mypool@snapshot1
* List snapshots: zfs list -t snapshot
* Backup a snapshot to a file: zfs send mypool@snapshot1 > mypool_snapshot_20180302
* Restore a snapshot from file: zfs receive mypool < mypool-snapshot_20180302

Other
* Destroy pool: zpool destroy mypool
* Check health of all pools: zpool status -x
