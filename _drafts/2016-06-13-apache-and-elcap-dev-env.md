---
title: "Setting Up Apache On El Capitan for a Dev Environment"
date: 2016-06-13
category: dev
---

Open `/etc/apache2/httpd.conf` and uncomment the two lines pertaining to virtual hosts:

    Include /private/etc/apache2/extra/httpd-vhosts.conf
    
    LoadModule vhost_alias_module libexec/apache2/mod_vhost_alias.so
    
Then edit `etc/apache2/extra/httpd-vhosts.conf`. There are examples in the file already, but you should add a block like this for all of your virtual hosts:

    <VirtualHost *:80>
        ServerAdmin webmaster@dummy-host2.example.com
        DocumentRoot "/usr/docs/dummy-host2.example.com"
        ServerName dummy-host2.example.com
        ErrorLog "/private/var/log/apache2/dummy-host2.example.com-error_log"
        CustomLog "/private/var/log/apache2/dummy-host2.example.com-access_log" common
    </VirtualHost>
    

this shit don't work...

try this instead: https://mallinson.ca/osx-web-development/
