Bash insights
=============

Jobs Jiu-jitsu
--------------

Move Job 123 into the foreground/background

```
fg $123
bg $123
```

List jobs

```
jobs
```

Start a job in background and don't close when logged out/terminal closes

```
nohup ./myscript.sh &
```

Functions
---------

```
function function1() {
}

function function2() {
	echo "$1";
	echo "$2";
}

# invoke the functions
function1;
function2 "param1" "param2";
```


Running a command remotely via ssh
----------------------------------

```
/usr/bin/ssh -t bob@192.168.1.5 -p 22 "/usr/local/bin/runthis"
```

Delay (seconds )
----------------

`sleep 3`

Check for existence of a file
-----------------------------
```
        if [ -e /home/todd/treasure ]
        then
                ...
        fi

```

Pipe a file to email
--------------------
```
cat /home/joe/test | mail -s "subject" bob@megaglobalcorp.com
```

Time a process
--------------

`time /usr/bin/slow`

Date Operations
---------------

```
date +'%Y-%m-%d'  # get date as string
date --date="$DATE_STRING" +%s  # parse date froms tring
```

Include another shell script (in the same folder--regardless of where execution happens)
------------------------------------------------------------------------------------
```
source "$(dirname $(readlink -f $0))/include.sh"
```

Make new lines work in echo
---------------------------

```
shopt -s xpg_echo
```
