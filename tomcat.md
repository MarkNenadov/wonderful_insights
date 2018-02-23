Apache Tomcat
==============

Old Version of WebSocket4Net (C# Library) Won't Connect To Tomcat 8.5.x
-----------------------------------------------------------------------

This has to do with old versions of WebSocket4Net requiring a reason phrase (which is optional in specs). This issue was fixed in WebSocket4Net 0.15.0-beta8 (so this fix is necessary only if you are stuck with supporting people who can't upgrade).

Fix is to add:

```
sendReasonPhrase="true"
```

to your Connector tag in conf/server.xml (it appears this approach will be deprecated in Tomcat 9.x).

Installing APR library for Tomcat 8.0.14/
-----------------------------------------

```
apt-get install libssl-dev libapr1-dev
wget http://apache.mirror.vexxhost.com/tomcat/tomcat-connectors/native/1.1.32/source/tomcat-native-1.1.32-src.tar.gz
tar xzf tomcat-native-1.1.32-src.tar.gz
cd tomcat-native-1.1.32-src/jni/native
./configure --with-apr=/usr/bin/apr-1-config -with-java-home=/usr/java/  -with-ssl=yes prefix=/usr/local/apache-tomcat-8.0.14/;
make
make install
cp /usr/local/apr/lib/* /usr/lib
```
