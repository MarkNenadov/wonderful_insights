Posfix insights
=============

Ban a Recipient by Email Address Exact Match
--------------------------------------------

1. Create /etc/postfix/transport and put the following into it:

```
email@toban.com discard

```

2. Add the following into main.cf:

```
transport_maps = hash:/etc/postfix/transport
```

3. Run the following

```
postmap /etc/postfix/transport
/etc/init.d/postfix restart
```


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
