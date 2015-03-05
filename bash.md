Bash insights
=============

Running a command remotely via ssh
----------------------------------

```
/usr/bin/ssh -t bob@192.168.1.5 -p 22 "/usr/local/bin/runthis"
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

Time a process
--------------

`time /usr/bin/slow`
