Apache insights
=============

Using proxy pass (in apache2.conf)
-----------------------------------
```
ProxyPreserveHost on

ProxyPass /here wss://localhost:8003/there
ProxyPassReverse /here wss://localhost:8003/there
```
