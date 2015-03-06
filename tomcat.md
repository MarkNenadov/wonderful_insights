Apache Tomcat
==============

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