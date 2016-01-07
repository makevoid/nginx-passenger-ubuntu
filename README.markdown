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

Parts from the old readme:

enjoy!

@makevoid

---

---

---

---

Installing git
----------------

    sudo apt-get install git-core

Nginx
-------
    
    
    gem install passenger --no-ri --no-rdoc
    passenger-install-nginx-module --auto --auto-download

     
Nginx init script (old /etc/init.d, for the new one see the systemd one)
-------------------

More information on http://wiki.nginx.org/Nginx-init-ubuntu

    cd
    git clone git://github.com/makevoid/nginx-passenger-ubuntu.git
    sudo mv nginx-passenger-ubuntu/nginx/nginx /etc/init.d/nginx
    sudo chown root:root /etc/init.d/nginx
    
Verify that you can start and stop nginx with init script

    sudo /etc/init.d/nginx start
    
      * Starting Nginx Server...
      ...done.
    
    sudo /etc/init.d/nginx status
    
      nginx found running with processes:  11511 11510
    
    sudo /etc/init.d/nginx stop
    
      * Stopping Nginx Server...
      ...done.
    
    sudo /usr/sbin/update-rc.d -f nginx defaults
    
If you want, reboot and see so the webserver is starting as it should.


## Optional:



Update and upgrade the system
-------------------------------

    sudo apt-get update
    sudo apt-get upgrade

Configure timezone
-------------------

    sudo dpkg-reconfigure tzdata
    sudo apt-get install ntp
    sudo ntpdate ntp.ubuntu.com # Update time
    
Verify that you have to correct date and time with

    date

Configure hostname
-------------------

    sudo hostname your-hostname

Add 127.0.0.1 your-hostname

    sudo vim /etc/hosts
    
Write your-hostname in 
    
    sudo vim /etc/hostname
    
Verify that hostname is set
    
    hostname
