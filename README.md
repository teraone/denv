# denv
Simple, efficient and highly configurable PHP development environment container for multiple projects.

Aim of the project
=======

To find the right development environment isn't an easy task. In the 'old days' we used XAMP/MAMP or other local webservers to test our code. Nowadays many developers prefer using Vagrant to build their own customized dev environment. These solutions are great tools, but none of them fit our needs. These are explicitly: 


 - easy to use
 - fast project switching
 - resource saving
 - configurable for each project
 - transportable config files
 - reproducible environment setup
 - platform independent (Unix, Windows)
 - open source / easy to extend by other developers
 - should closely mirror the production environment 
 - do not rely on host services ( no mysql server needs to be installed on your laptop)

 
 Furthermore there are some things we do not want to do
 
 - edit the hosts file
 - change my host system (my laptop is my castle)
  
 
 
How could this be solved?
=======

Rough structure:  
 
 - Service Container (optional)
    - mysql
    - memcached
    - mongo
    - mailcatcher (oder ähnlich)    
    - ...
    
 - Main Container
    - Executes PHP 
    - includes dns server? This would enable access from external devices in local network to project websites. Maybe even access over internet.  


How should things be configured?
=======

denv config
- global denv-config file. Includes project symlinks (saved on host machine, not in project folder)
- project config file to define the dependencies (services etc)



These settings should be configurable for each project:
 - PHP Engine: PHP or HHVM
 - Engine version: for example PHP 5.4.19
 - Webserver NGINX or Apache
 - No need to choose webserver version (?!)
 - PHP
    - Extensions (pdo, pdo_mysql, memcache,  ...)
    - php.ini file 
 - Webserver configuration file (httpd.conf)
 
 
