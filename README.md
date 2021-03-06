## Vagrant virtual machine with Ubuntu 16.04 and clean Drupal 8.x
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
>
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
     
 
That's it, now go to http://192.168.168.168 on your host machine
   &
enjoy :sunglasses:

===
Note - first boot might be slow (20-30 sec ) that's drupal is warming up cache and stuff


### If default NFS is slow try rsync:
### File sync:

Use rsync to immediately push any changes from your host to guest

To do that - go to project root and run:

    vagrant rsync-auto

To sync files from guest to host install vagrant plugin **vagrant-rsync-back** 

    vagrant plugin install vagrant-rsync-back

and then every time you need to pull changes from your guest back to your host machine run

    vagrant rsync-back
