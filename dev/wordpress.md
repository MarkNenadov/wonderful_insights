Wordpress Insights
==================

Set proper permissions for direct/automatic updates
---------------------------------------------------

```
chown www-data:www-data -R *;
find . -type d -exec chmod 755 {} \;
find . -type f -exec chmod 644 {} \;
```
