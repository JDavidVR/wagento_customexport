# Wagento Customexport

##Installation

* create directory `/app/Wagento/Bundle`
* clone project in created path `git clone git@github.com:JDavidVR/wagento_customexport.git CustomExportBundle`
* open file `app/AppCache.php` add `new Wagento\Bundle\CustomExportBundle\WagentoCustomExportBundle(),` to `protected function registerProjectBundles()`

```php
/**
  * Registers your custom bundles
  *
  * @return array
  */
 protected function registerProjectBundles()
 {
     return [
         // your app bundles should be registered here
         new Wagento\Bundle\CustomExportBundle\WagentoCustomExportBundle(),
     ];
 }
```
* on terminal execute following commands on your akeneo ROOT dir

```
php -d memory_limit=3G ../composer.phar install --optimize-autoloader --prefer-dist; 
yarn install;
```

* to clean cache execute: 

```
rm -rf ./var/cache/*;  bin/console assets:install --symlink web; 
yarn run webpack;
```
* login to your akeneo instance and go to `System > System > Information `  it must list module in Registered Bundles

```
Akeneo\Bundle\BatchBundle\AkeneoBatchBundle
Symfony\Bundle\SecurityBundle\SecurityBundle
Symfony\Bundle\SwiftmailerBundle\SwiftmailerBundle
Symfony\Bundle\TwigBundle\TwigBundle
    .
    .
    .
Wagento\Bundle\CustomExportBundle\WagentoCustomExportBundle <--installed succesfully
```