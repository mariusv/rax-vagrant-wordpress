# Rackspace Vagrant, Apache, Puppet base repo


## Installation
####This setup is based and tested with Ubuntu Precise 64 bit base box, with Vagrant 1.2.7 version (should be vorking with 1.3.4)

* Install Vagrant using using the [installation instructions](http://docs.vagrantup.com/v2/installation/index.html)
* Clone this repository

    ```$ git clone https://github.com/MikeRogers0/vagrant-nginx-wordpress-puppet.git```
    
* install git submodules
    ```$ git submodule update --init```

* run vagrant (for the first time it should take up to 10-15 min)
    ```$ vagrant up --provider=rackspace```
    
* Vagrant automatically setups database with this setup:

    * Username: wordpress
    * Password: wordpress-vagrant
    * Database: wordpress

## Installed components
* Wordpress Latest 
* [Apache2](http://apache.org/)
* [MySQL](http://www.mysql.com/)
* [PHP5](http://php.net/) 
* [PEAR](http://pear.php.net/)
* [cURL](http://curl.haxx.se/)
* [Imagic](http://www.imagemagick.org/script/index.php)

## TODO

* Add Nginx and PHP-FPM  support
* Different endpoins for Rackspace as now is supporting only U.K
* Clean the code and organise it :-)
