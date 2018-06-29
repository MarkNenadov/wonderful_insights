Rsync Insights
=================

A Fairly Typical Sync
---------------------

rsync -av -e "ssh -l root -p 22" "/home/data/" "192.168.1.15:/home/data/" -- exclude "*lockfile.pid"
