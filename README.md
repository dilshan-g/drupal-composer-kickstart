# drupal-composer-kickstart
Provides a puphpet based virtual environment with a Drupal installation

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
