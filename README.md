# dynmotd
Dynamic Motd (Message of the Day) an old script to print out some system-specific information.


![Example](/data/dynmotd.png)


Requirements
------------

awk, egrep, sed, whoami, hostname, touch, source, rm, who, sort, uniq, tty, ps, ulimit, groups, cat, cut, wc, uptime, bc, uname, host, id, bash, df, 

Installation
------------

Script runs only as root.

~~~
sudo -i
git clone https://github.com/rtulke/dynmotd.git
cd dynmotd
mv dynmotd.sh /usr/local/bin/dynmotd
chmod 777 /usr/local/bin/dynmotd
echo "/usr/local/bin/dynmotd" > /etc/profile.d/motd.sh
~~~

Test dynmotd

~~~
exit
sudo -i
~~~

Parameter 
---------

~~~
Usage: ./dynmotd [-c|-a|-d|--help] <params>

    e.g. ./dynmotd -a "start web migration"

    Parameter:

      -a | addlog  | --addlog "..."           add new log entry
      -d | rmlog   | --rmlog [loglinenumber]    delete specific log entry
      -l | log     | --log                      list complete log
      -c | config  | --config                   configuration setup
~~~

Some dynmotd Options
--------------------

~~~
vim /usr/local/bin/dynmotd
~~~

You can enable or disable information blocks 

~~~
## enable system related information about your system
SYSTEM_INFO="1"
STORAGE_INFO="1"
USER_INFO="1"
ENVIRONMENT_INFO="1"
MAINTENANCE_INFO="0"
VERSION_INFO="1"
~~~

 * 1 = enable
 * 0 = disable

You can also change the log message line lenght by modify "LIST_LOG_ENTRY"

~~~
LIST_LOG_ENTRY="5"
~~~
