Posfix insights
=============

Get count of items in postfix queue
-----------------------------------
mailq | find /var/spool/postfix/deferred -type f | wc -l
