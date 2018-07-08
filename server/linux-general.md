General Linux Insights
======================

Unless otherwise mentioned, I assume Ubuntu as the distribution

For Laptops, turn off the lid close hibernate
---------------------------------------------

Edit /etc/systemd/logind.conf:

```
HandleLidSwitch=ignore
```


List Installed Packages
-----------------------

`dpkg --get-selections | grep -v deinstall`

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

Installing Multiple PHP Versions on Ubuntu
------------------------------------------

* The directions in this link work well: https://www.tecmint.com/install-different-php-versions-in-ubuntu/amp/

Get JDK
-------

```
wget --no-check-certificate --no-cookies --header "Cookie: oraclelicense=accept-securebackup-cookie" http://download.oracle.com/otn-pub/java/jdk/8u172-b11/a58eab1ec242421181065cdc37240b08/jdk-8u172-linux-x64.tar.gz;
```