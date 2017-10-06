JSoup (Java Scrapping Library) Insights
========================================

Selectors
---------

Here are some example document.select() queries covering various usecases:

1. Get the contents of the first span tag with  particular class (classname)

```
document.select( "span.classname" ).first().text()
```

2. Get the href of all a tags which have an href starting with "http://maps.google.com":

```
document.select( "a[href^=http://maps.google.com" ).attr( "href" )
```