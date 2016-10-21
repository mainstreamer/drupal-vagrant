## Vagrant virtual machine with clean Drupal 8.x inside
#### Requirements:
* Vagrant
* Virtual box
* Composer

#### VM specs:
* Ubuntu 16.04
* PHP 7.0
* Mysql 5.7 (user: root  pass: root)
* Drupal 8.x (http://localhost:8888)

> ## Installation:
> 
>1)   clone repo
>     git clone git@github.com:mainstreamer/drupal-vagrant.git
>2)   cd into project and run:
> 
>     composer install
>3)   then to create virtual environment run:
> 
>     vagrant up
>4)   ssh into your virtual machine:
> 
>     vagrant ssh
>5)   run bootstrap script:
> 
>     cd /vagrant
>     ./bootstrap-vm.sh
     
That's it, now go to localhost:8888 on your host machine
   &
enjoy :)


Note - first boot might be slow (20-30 sec ) that's drupal is warming up cache and stuff

### File sync:
cd into project and run:
 
     composer install

Use rsync to immediately push any changes from your host to guest

To do that - go to project root and run:

    vagrant rsync-auto

to sync files from guest to host install vagrant plugin **vagrant-rsync-back** and run

    vagrant rsync-back

You need to run this every time you need to pull changes from your guest back to your host machine

