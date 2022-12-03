# DVWA Setup in Kali Linux

## Open Home Terminal 1

```
git clone https://github.com/digininja/DVWA.git
```

```
sudo mv DVWA /var/www/html
```

```
cd /var/www/html
```

```
sudo service apache2 start
```

```
cd DVWA
```

```
cp config/config.inc.php.dist config/config.inc.php
```

```
sudo service mariadb start
```

### Now Open a New Root Terminal 2

```
mysql
```

```
create database dvwa;
```

```
create user dvwa@localhost identified by 'p@ssw0rd';
```

```
grant all on dvwa.* to dvwa@localhost;
```

```
flush privileges;
```

### Return to the Previous Home Terminal 1

```
gedit config/config.inc.php
```

NOTE: In the file opened above in editor the useful information like Credentials is availabe for DVWA on working Server.

### Open new Home Terminal 3

```
mysql -u dvwa -pp@ssw0rd
```

### Return to Home Terminal 1

```
sudo su
```

```
cd /etc/php
```

```
cd 8.1
```

```
cd apache2
```

```
vim php.ini
```

Type the Following as soon as the file opens: /allow_url_include

Then change the it from Off to On

Now type the following to quit Vim Editor: :wq

Now continue in the terminal

```
apt update
```

```
apt install php-gd
```

```
chown www-data /var/www/html/hackable/uploads/
```

```
chown 777 /var/www/html/hackable/uploads/
```

```
chown www-data /var/www/html/DVWA/external/phpids/0.6/lib/IDS/tmp/phpids_log.txt
```

```
chown www-data /var/www/html/DVWA/config
```

```
apachectl restart
```

## Open Firefox

Type the following address in the address bar.

```
http://localhost
```

It shows the apache service is available now add the address provided below in the same tab.

```
http://localhost/DVWA/setup.php
```
