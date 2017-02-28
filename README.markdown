nginx-passenger-ubuntu
============================


Forked from @jnstq, added also the `systemd` and the `upstart` scripts, choose your favourite

---

## Systemd setup:

Here's a quick `systemd` setup using the config / startup file contained in this repo:


    systemctl stop nginx
    curl https://raw.githubusercontent.com/makevoid/nginx-passenger-ubuntu/master/nginx/nginx.service > /lib/systemd/system/nginx.service
    systemctl daemon-reload
    systemctl enable nginx
    systemctl start nginx
    systemctl status nginx

For more info visit:

- https://www.nginx.com/resources/wiki/start/topics/examples/systemd/
- https://wiki.ubuntu.com/SystemdForUpstartUsers#Commands
- https://wiki.archlinux.org/index.php/Systemd
- https://www.nginx.com/resources/wiki/start/topics/tutorials/commandline/

----


enjoy!

@makevoid
