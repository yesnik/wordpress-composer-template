# Wordpress Composer Template

Use this template for your next Wordpress project. It will help you to install themes and plugins via *composer* from https://wpackagist.org/ .

## Installation

* Clone this repo:

```
git clone ...
```

* Install dependencies:

```
cd wordpress-composer-template
composer install
```

* Start development server:

```
php -S 127.0.0.1:8000
```

* Open [link](http://127.0.0.1:8000) in browser. Enter DB credentials. After this you'll see autogenerated `wp/wp-config.php` file.

* Move autogenerated `wp-config.php` file to the root of this project:

```
cd wordpress-composer-template
mv wp/wp-config.php ./wp-config.php
```

* Edit `wp-config.php`. Place this code before the comment `/* That's all, stop editing! Happy blogging. */`:

```php
// Define site URL
define('SITE_URL', 'http://' . $_SERVER['HTTP_HOST']);

// Define custom wp-content dir
define('WP_CONTENT_DIR', dirname(__FILE__) . '/wp-content');
// Define custom wp-content URL
define('WP_CONTENT_URL', SITE_URL . '/wp-content');

// Define Plugin DIR
define('WP_PLUGIN_DIR', dirname(__FILE__) . '/wp-content/plugins');
// Define Plugin URL
define('WP_PLUGIN_URL', SITE_URL . '/wp-content/plugins');
// Define this constant to solve possible compatability issues
define('PLUGINDIR', WP_PLUGIN_URL);

/* That's all, stop editing! Happy blogging. */

// ...
```

This constants make Wordpress to use different folders for wp-content, plugins and themes.

* Visit your site: http://127.0.0.1:8000 . Happy coding!

## Describe directory structure

- `wp/` - folder for Wordpress Core
- `wp-content/plugins` - folder for plugins
- `wp-content/themes` - folder for themes
- `wp-content/uploads` - folder for user uploads (we need to backup it regurally to have a chance to restore our site's files)
- `wp-content/vendor` - folder for installed composer packages

## Commands

* Install plugin from wpackagist.org

```
composer require wpackagist-plugin/all-in-one-seo-pack
```

* Install theme from wpackagist.org

```
composer require wpackagist-theme/philips
```

## Useful links

- https://composer.rarst.net/
- https://github.com/wodby/wordpress-composer
