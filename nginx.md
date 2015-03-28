nginx
=====

Sample Statically Hosted Virtual Host Config
--------------------------------------------

```server {
        listen       80;
        server_name  nhl.com www.nhl.com;
        access_log  logs/nhl.access.log;

        location / {
                index index.html;
                root /websites/nhl/;
        }

        error_page   500 502 503 504  /50x.html;
    }```

Sample Virtual Host Passed Over To Apache
-----------------------------------------

```server {
        listen       80;
        server_name  mywordpresssite.com www.mywordpresssite.com;
        access_log  logs/mywordpresssite.access.log;

        location / {
                proxy_pass http://127.0.0.1:81;
                proxy_set_header Host $host;
                proxy_set_header X-Real-IP $remote_addr;
        }

        error_page   500 502 503 504  /50x.html;
        location = /50x.html {
            root   html;
        }
    }```
