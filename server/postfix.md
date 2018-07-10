Posfix insights
=============

Get count of items in postfix queue
-----------------------------------

```
mailq | find /var/spool/postfix/deferred -type f | wc -l
```

Delete Postfix Deferred Items Based on text in the body of the emails
---------------------------------------------------------------------

```
find /var/spool/postfix/deferred/ -type f -exec grep -l 'Email body text to look for.' '{}' \; | xargs -n1 basename | xargs -n1 postsuper -d
```
