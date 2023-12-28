---
title: "Setting up Wordpress"
date: "2016-05-22"
categories: 
  - "linux"
  - "ubuntu"
  - "webtech"
  - "wordpress"
---

The following instructions describe how I install Wordpress on Ubuntu. The instructions may differ slightly for other server environments, but the basic principles should be the same. This requires shell access to the server, but once it's finished the Wordpress instance(s) should be capable of being administered through a web browser.

### Part 1 - Installing Wordpress

Download Wordpress and move it to `/var/www/html/` so it runs from the root directory of the web server.

`cd /var/www/html`  
`sudo apt-get install unzip`  
`sudo wget http://wordpress.org/latest.zip`  
`sudo unzip latest.zip`  
`cd wordpress`  
`sudo mv * /var/www/html/`  
`cd /var/www/html`  
`sudo mv index.html index.html_old`

Log into mysql:

`mysql -u root -p`

Create a new database (calling it something different to the example below)

`mysql> CREATE DATABASE wordpress;`  
`mysql> GRANT ALL PRIVILEGES ON wordpress.* TO wp_user@localhost IDENTIFIED BY "<password>";`  
`mysql> exit`

Install Wordpress, following the instructions at [http://codex.wordpress.org/Installing\_WordPress](http://codex.wordpress.org/Installing_WordPress). Remember to make a note of the username and password you set up for the admin account.

At one point in the installation (it will be obvious) you may need to issue the following command to manually create a config file.

`sudo nano wp-config.php`

Once Wordpress is installed, navigate to `/var/www` (`cd ..` or `cd /var/www/`) and issue the following command:

`sudo chown -R www-data html`

This will ensure you can install plugins and themes through the Wordpress web interface.

* * *

### Part 2 - Configuring Wordpress

Log in using the account you just created.

Install and activate some plugins (Acunetix WP Security, Jetpack by WordPress.com, WP-Markdown and WordPress Importer), via the web interface in Wordpress (if you've not issued the command above then this won't work).

Navigate to the left hand menu item for Acunetix WP Security, tick all boxes and click on "update settings". This will apply all recommended security changes.

Use Wordpress Importer to import content (posts, tags, files) from other instances of Wordpress.

If you want to compose posts in markdown then you'll need to navigate to Settings --> Writing and tick the boxes for the interfaces you want to default to markdown.

_Note: you won't be able to activate Jetpack unless the server is visible on the public internet._

Remove the "Hello World!" post and the sample page (both should be obvious if they have not been removed!)

* * *

### Part 3 - Wordpress Multisite (optional)

This allows you to run more than one blog/site in a single instance of Wordpress. The instructions at [http://codex.wordpress.org/Create\_A\_Network](http://codex.wordpress.org/Create_A_Network) are good, and are mostly enough to get it up and running.

There are two more things to do on Ubuntu servers:

Enable `mod_rewrite`

```
 a2enmod rewrite
```

Open `/etc/apache2/apache2.conf` and find the part that says:

```
 <Directory /var/www/>
 Options Indexes FollowSymLinks
 AllowOverride None
 Require all granted
 </Directory>
```

Replace `AllowOverride None` with `AllowOverride All`

* * *

### Part 4 - SSL (optional)

Enable `mod_rewrite` (if you've not already done it as part of step 3)

`sudo a2enmod rewrite`

Enable ssl

`sudo a2enmod ssl`  
`sudo a2ensite default-ssl.conf`

Amend your apache config to enable pages to be served on port 443

`sudo nano /etc/apache2/sites-available/default-ssl.conf`

```
<VirtualHost _default_:443>
Servername yourdomain.com
DocumentRoot /var/www/html

#Enable/Disable SSL for this virtual host.
SSLEngine on
SSLProtocol all -SSLv2 -SSLv3
```

Amend 80 config (e.g. 000-default.conf), to redirect to 443

`sudo nano /etc/apache2/sites-available/000-default.conf`

```
DocumentRoot /var/www/html
ServerName yourdomain.com
Redirect "/" "https://yourdomain.com"
```

Restart apache

`sudo service apache2 restart`

Change domain in WordPress settings (through UI) to `yourdomain.com`

Create a certificate request (csr):

`sudo mkdir /etc/apache2/ssl`  
`sudo openssl req -new -newkey rsa:2048 -nodes -keyout /etc/apache2/ssl/yourdomain.key -out /etc/apache2/ssl/yourdomain.csr`

```
Country Name (2 letter code) [XX]:GB
State or Province Name (full name) []:West Midlands
Locality Name (eg, city) [Default City]:Your city
Organization Name (eg, company) [Default Company Ltd]:Your Company
Organizational Unit Name (eg, section) []:
Common Name (eg, your name or your server's hostname) []:yourdomain.com
```

Copy certificate somewhere sensible

`sudo cp /etc/apache2/ssl/yourdomain.csr /home/username/yourdomain.csr`

What you'll need to do then is grab the certificate from home directory, save it somewhere safe and then do whatever you do in your organisation/environment to generate/buy/get a root certificate (there are so many different ways).

Once you have a root certificate, follow instructions at http://askubuntu.com/questions/73287/how-do-i-install-a-root-certificate

Configure apache to use certificate

`sudo nano /etc/apache2/sites-available/default-ssl.conf`

Then add/edit the following lines:

```
SSLEngine on
SSLProtocol all -SSLv2 -SSLv3
SSLCertificateFile  /etc/apache2/ssl/yourdomain.com.cer
SSLCertificateKeyFile /etc/apache2/ssl/yourdomain.key
```

Restart apache

`sudo service apache2 restart`

At that point your site should serve web pages on https with no error messages.
