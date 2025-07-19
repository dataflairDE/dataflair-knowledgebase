## Do You Want to Install MariaDB (MySQL) on Your Server?


Update the Server Package List
``` bash
apt update && apt upgrade -y
```

Install MariaDB and Required Packages
``` bash
apt install ca-certificates apt-transport-https lsb-release gnupg curl nano unzip -y
```

``` bash
apt install software-properties-common -y
```

``` bash
add-apt-repository ppa:ondrej/php
```

``` bash
apt update
```

``` bash
apt install apache2 -y
```

``` bash
apt install php7.4 php7.4-cli php7.4-common php7.4-curl php7.4-gd php7.4-intl php7.4-json php7.4-mbstring php7.4-mysql php7.4-opcache php7.4-readline php7.4-xml php7.4-xsl php7.4-zip php7.4-bz2 libapache2-mod-php7.4 -y
```

``` bash
apt install mariadb-server mariadb-client -y
```

``` bash
mysql_secure_installation
```

Install phpMyAdmin
``` bash
cd /usr/share
```

``` bash
wget https://www.phpmyadmin.net/downloads/phpMyAdmin-latest-all-languages.zip -O phpmyadmin.zip
```

``` bash
unzip phpmyadmin.zip
```

``` bash
rm phpmyadmin.zip
```

``` bash
mv phpMyAdmin-*-all-languages phpmyadmin
```

``` bash
chmod -R 0755 phpmyadmin
```

Configure Apache for phpMyAdmin
``` bash
nano /etc/apache2/conf-available/phpmyadmin.conf
```
*!! Paste the following configuration !!*

``` bash
# phpMyAdmin Apache configuration

Alias /phpmyadmin /usr/share/phpmyadmin

<Directory /usr/share/phpmyadmin>
    Options SymLinksIfOwnerMatch
    DirectoryIndex index.php
</Directory>

# Disallow web access to directories that don't need it
<Directory /usr/share/phpmyadmin/templates>
    Require all denied
</Directory>
<Directory /usr/share/phpmyadmin/libraries>
    Require all denied
</Directory>
<Directory /usr/share/phpmyadmin/setup/lib>
    Require all denied
</Directory>
```

Activating the configuration
``` bash
a2enconf phpmyadmin
```

``` bash
systemctl reload apache2
```

Create Temporary Directory for phpMyAdmin
``` bash
mkdir /usr/share/phpmyadmin/tmp/
```

``` bash
chown -R www-data:www-data /usr/share/phpmyadmin/tmp/
```

*(Optional) Create an Additional user*
``` bash
mysql -u root
```

``` bash
CREATE USER 'username'@'localhost' IDENTIFIED BY 'password';
```

``` bash
GRANT ALL PRIVILEGES ON *. * TO 'username'@'localhost' WITH GRANT OPTION
```

``` bash
exit
```

© dataflair – Republishing this guide on external websites is not permitted.