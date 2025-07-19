## Sie möchten MariaDB (MySQL) auf Ihren Server installieren?


Server-Paketliste aktualisieren
``` bash
apt update && apt upgrade -y
```

MariaDB und benötigte Pakete installieren
``` bash
apt install ca-certificates apt-transport-https lsb-release gnupg curl nano unzip -y
```

``` bash
curl -fsSL https://packages.sury.org/php/apt.gpg -o /usr/share/keyrings/php-archive-keyring.gpg
```

``` bash
echo "deb [signed-by=/usr/share/keyrings/php-archive-keyring.gpg] https://packages.sury.org/php/ $(lsb_release -sc) main" > /etc/apt/sources.list.d/php.list
```

``` bash
apt update
```

``` bash
apt install apache2 -y
```

``` bash
apt install php8.2 php8.2-cli php8.2-common php8.2-curl php8.2-gd php8.2-intl php8.2-mbstring php8.2-mysql php8.2-opcache php8.2-readline php8.2-xml php8.2-xsl php8.2-zip php8.2-bz2 libapache2-mod-php8.2 -y
```

``` bash
apt install mariadb-server mariadb-client -y
```

``` bash
mysql_secure_installation
```

phpMyAdmin installieren
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

Apache für phpMyAdmin konfigurieren
``` bash
nano /etc/apache2/conf-available/phpmyadmin.conf
```
*!! Fügen Sie die folgende Konfiguration ein !!*

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

Konfiguration aktivieren
``` bash
a2enconf phpmyadmin
```

``` bash
systemctl reload apache2
```

Temporäres Verzeichnis für phpMyAdmin erstellen
``` bash
mkdir /usr/share/phpmyadmin/tmp/
```

``` bash
chown -R www-data:www-data /usr/share/phpmyadmin/tmp/
```

*(Optional) Einen zusätzlichen Benutzer erstellen*
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

© dataflair - Die Weiterveröffentlichung dieser Anleitung auf externen Webseiten ist nicht erlaubt.