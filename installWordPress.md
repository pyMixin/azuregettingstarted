# Install Apache, MySQL and PHP on Azure Virtual Machine

## Install LAMP

    sudo apt update && sudo apt install lamp-server^

## Verify Apache 

    apache2 -v
  

## Verify PHP

    php -v
  
## Install WordPress

    sudo apt install wordpress

## Configure the configuration file

    sudo vi /etc/wordpress/config-localhost.php
    <?php
    define('DB_NAME', 'wordpress');
    define('DB_USER', 'wordpress');
    define('DB_PASSWORD', 'yourPassword');
    define('DB_HOST', 'localhost');
    define('WP_CONTENT_DIR', '/usr/share/wordpress/wp-content');
    ?>
  
## Move the WordPress installation to the web server document root

    sudo ln -s /usr/share/wordpress /var/www/html/wordpress
    sudo mv /etc/wordpress/config-localhost.php /etc/wordpress/config-default.php

Now you can complete the WordPress setup and publish on the platform. Open a browser and go to http://<YOUR_IP>/wordpress
