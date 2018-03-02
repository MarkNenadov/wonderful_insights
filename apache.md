Apache insights
=============

Using proxy pass with Web Sockets (in apache2.conf)
----------------------------------------------------
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
