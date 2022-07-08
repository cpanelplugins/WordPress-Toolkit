# Overview
The WordPress Toolkit plugin allows you to easily install, configure, and manage WordPress®.

# Install WordPress Toolkit

You can install the WordPress Toolkit plugin with the following methods:

1. The WHM Marketplace
2. Manual installation

You may confirm WordPress Toolkit installation by accessing WHM’s WordPress Toolkit interface (WHM >> Home >> Plugins >> WordPress Toolkit). If enabled, cPanel users can also access this plugin in cPanel’s WordPress Toolkit interface (cPanel >> Home >> Domains >> WordPress Toolkit).

When you install the WordPress Toolkit, the system automatically installs the PHP-FPM Service for cPanel Daemons. The system also enables the PHP-FPM Service for cPanel Daemons when you update or remove WordPress Toolkit from the server.

## WHM Marketplace

To install the WordPress Toolkit plugin in the WHM Marketplace interface (WHM >> Home >> Server Configuration >> WHM Marketplace), perform the following steps as the root user:

Navigate to the WHM Marketplace interface (WHM >> Home >> Server Configuration >> WHM Marketplace).
Locate the WordPress Toolkit listing under Add Extensions and click Install.

## Manual installation


To install the WordPress Toolkit plugin on the command line, run the following command as the root user:

`sh <(curl https://wp-toolkit.plesk.com/cPanel/installer.sh || wget -O - https://wp-toolkit.plesk.com/cPanel/installer.sh)`


# WHM configuration

You must fulfill these requirements to use the WordPress Toolkit plugin:

- WordPress only supports MySQL® version 5.7 and later. To update your server’s version of MySQL to 5.7 and later, use WHM’s MySQL/MariaDB Upgrade interface (WHM >> Home >> SQL Services >> MySQL/MariaDB Upgrade).
- Enable the PHP-FPM Service for cPanel Daemons, which must remain enabled to use the WordPress Toolkit.
- To enable any required WordPress PHP extensions, use the PHP Extensions section of WHM’s EasyApache 4 interface (WHM >> Home >> Software >> EasyApache 4). For a list of these PHP extensions, read WordPress’ Server Environment documentation. To update your server’s PHP version, use WHM’s EasyApache interface (WHM >> Home >> Software >> EasyApache 4).
- The WordPress Toolkit plugin requires a PHP memory_limit value of 128 MB or higher. You can set this limit in WHM’s MultiPHP INI Editor interface (WHM >> Home >> Software >> MultiPHP INI Editor).
- In the Feature Manager, enable the following features: WordPress Toolkit, MySQL, Subdomains, MIME Types, Cronjobs, Directory Privacy, Password & Security, File Manager, Redirects

For information about software versions WordPress requires to run properly, read WordPress’ Requirements documentation.


# Enable Deluxe features

WordPress Toolkit is available in a standard version and a Deluxe version. To use WordPress Toolkit Deluxe features, enable both the WordPress Toolkit and WordPress Toolkit Deluxe features in the Feature Manager.

# Updates to WordPress Toolkit

Updates to the WordPress Toolkit run nightly.

To check the system’s auto-update status, run the following command as the root user:

`systemctl status wp-toolkit-scheduled-tasks`

To force an auto-update run, run the following command as the root user:

`su wp-toolkit --shell=/bin/bash -c '/usr/bin/sw-engine -d auto_prepend_file=/usr/local/cpanel/3rdparty/wp-toolkit/scripts/scheduled-task-prepend-file.php /usr/local/cpanel/3rdparty/wp-toolkit/plib/scripts/instances-auto-update.php'`

# Troubleshoot WordPress Toolkit

