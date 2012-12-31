centos5-uwsgi-init-script
=========================


Centos 5 uWSGI init.d script


====
Script to start/stop/restart/relaod uWSGI on Centos-5.


"Install" Notes:

- Copy/Paste or Download the file to "/etc/init.d/uwsgi"
- Adapt the variables acording to you're setup:
  PROG=/usr/bin/uwsgi
  DESC=uWSGI
  DAEMON_OPTS="-x /etc/uwsgi/uwsgi.xml" 
  
- Change the permission to allow the file to execute:
    chmod +x /etc/init.d/uwsgi


Aditional Notes:

The script uses "/etc/uwsgi/uwsgi.xml" which should contain the config.

Example:
<uwsgi>
        <uid>uwsgi</uid>
        <gid>uwsgi</gid>
        <socket>/var/run/uwsgi/uwsgi.socket</socket>
        <pythonpath>/var/www/myapp/</pythonpath>
        <master>true</master>
        <pidfile>/var/run/uwsgi/wsgi.pid</pidfile>
        <workers>2</workers>
        <module>wsgi</module>
        <enable-threads>true</enable-threads>
        <daemonize>/var/log/uwsgi.log</daemonize>
</uwsgi>

Antoher file or config can be pointed by changing the "DAEMON_OPTS" var inside "uwsgi" init script!

