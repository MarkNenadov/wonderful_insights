== Websockets ==

-- Serving Up WSS to Resin/Tomcat app server Using Apache's SSL Cert --

Basically, this allows you to share the SSL certificate between your WSS functionality and the rest of your websites, ie. avoiding having to serve the websockets on a different port or a different subdomain.

1. Install mod_proxy_wstunnel (I had to patch it to fix a bug in its wss support)
2. Use mod_proxy ProxyPass directives to forward requests from Apache to app server
3. Note: I recommend using Tomcat for this instead of Resin. Had issues with Resin due to shoddy websocket implementation.
