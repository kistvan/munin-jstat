# 1.Install

    $ cd /usr/share/munin/plugins/
    $ sudo wget https://raw.github.com/kistvan/munin-jstat/master/jstat-gcutil -O jstat-gcutil
    $ sudo chmod a+x jstat-gcutil
    $ sudo ln -s /usr/share/munin/plugins/jstat-gcutil /etc/munin/plugins/jstat-gcutil
    $ sudo -e /etc/munin/plugin-conf.d/munin-node

edit munin-node config file.

    [jstat-gcutil]
    user root # root or java application PID accessible user
    env.JAVA_HOME /usr/java/latest #default /usr/java/latest

test and run.

    $ sudo munin-run jstat-gcutil
    $ sudo service munin-node reload

