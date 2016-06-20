# drupal-composer-kickstart
Provides a puphpet based virtual environment with a Drupal installation

### prerequisites

To run this vm you should install the below list:

- Vagrant 1.8.*
- VirtualBox latest version
- vagrant-hostsupdater plugin
   - You don't have to worry about adding box ip into your etc/hosts when you have this plugin.
- Composer latest version
- Git latest version

### Installation

This simple drupal based vm can be setup using few steps:

1) Clone the repository `git@github.com:dilshan-g/drupal-composer-kickstart.git`.

2) Go inside the drupal-composer-kickstart folder and execute 'vagrant up'.
   - This will take 5 - 10 minutes, depending on your hardware.

3) Execute `composer install/update`.
   - This will install all the dependencies required to bootstrap Drupal 7.

4) Once the step three is done, you have to do a `vagrant reload`.
   - This is because, composer will put all drupal files/folders inside the html folder of your project root, we have to sync those files into `/var/www/html` in our vm.
   
5) As the final step execute.
`drush si standard --site-name=Test --account-name=admin --account-pass=admin --account-mail=test@example.com --db-url=mysql://root:123@localhost/test1`
   - This will install Drupal 7 inside the vm

6) Go to http://mydrupalsite.dev/ of your browser and Done !

##### Note : if you don't have vagrant-hostupdater installed, you must maually add this entry to your hosts. `192.168.56.101  mydrupalsite.dev`

### Compatibility 

I have tested this on both OS X El Capitan and Ubuntu 16.04 (Xenial Xerus), But not tested on Windows.

### Where to go from here

This vm installs only the Drupal standard profile with few necessary modules. I have added few dependencies which are commonly used by developers. 
 - You can try creating your own profile to add more modules to build your own site.
 - You can install more dependencies to composer in order to build your site. Such as rocketeer for deployments, elasticsearch to index documents for search. You only need to run a simple commad like this to add any dependency `composer require drupal/coder 8.2.4` 
 - Or if you are an out of the box thinker, try creating a vm for your preferred PHP Framework/CMS using this repository as a base.  


 

