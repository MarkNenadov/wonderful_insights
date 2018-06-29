Websockets
==========

Serving Up WSS to Resin/Tomcat app server Using Apache's SSL Cert
-----------------------------------------------------------------

Basically, this allows you to share the SSL certificate between your WSS functionality and the rest of your websites, ie. avoiding having to serve the websockets on a different port or a different subdomain.

1. Install mod_proxy_wstunnel (For older Apache, I had to patch it to fix a bug in its wss support. For Apache 2.4 you can just go ahead and enable the proxy and proxy_wstunnel modules )
2. Use mod_proxy ProxyPass directives to forward requests from Apache to app server
3. Note: I recommend using Tomcat for this instead of Resin. Had issues with Resin due to shoddy websocket implementation.

Proxying Websocket Requests
---------------------------

If, for whatever reason you want to proxy websocket requests, check out this project: https://github.com/MarkNenadov/websocket_proxpy .. No guarantees, but it is a simple implementation of that.

Make your javascript websocket code auto reconnect
--------------------------------------------------

* https://github.com/joewalnes/reconnecting-websocket

Turn stdin/stdout programs into Websocket servers
-------------------------------------------------

* http://websocketd.com/
