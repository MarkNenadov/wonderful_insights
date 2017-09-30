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