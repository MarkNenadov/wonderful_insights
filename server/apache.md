Apache insights
=============

Using proxy pass with Web Sockets 
----------------------------------------------------

Run these commands to enable the required modules:

```
a2enmod ssl;
a2enmod proxy;
a2enmod proxy_wstunnel;
a2enmod authz_groupfile;
/etc/init.d/apache2 restart;
```

Put this into your config:

```
ProxyPreserveHost on

ProxyPass /here wss://localhost:8003/there
ProxyPassReverse /here wss://localhost:8003/there
```
Alternately (and IMO, cleaner):

```
ProxyPreserveHost on

<LocationMatch "/here">
   ProxyPass wss://localhost:8003/there
   ProxyPassReverse wss://localhost:8003/there
</LocationMatch>
```
