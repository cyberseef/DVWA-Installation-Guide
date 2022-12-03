# DVWA Setup in Kali Linux

## Open Home Terminal 1

```ruby
git clone https://github.com/digininja/DVWA.git
```

```ruby
sudo mv DVWA /var/www/html
```

```ruby
cd /var/www/html
```

```ruby
sudo service apache2 start
```

```ruby
cd DVWA
```

```ruby
cp config/config.inc.php.dist config/config.inc.php
```

```ruby
sudo service mariadb start
```

### Now Open a New Root Terminal 2

```ruby
mysql
```

Now database configurations will open up so type the commands below.

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

```ruby
gedit config/config.inc.php
```

NOTE: In the file opened above in editor the useful information like Credentials is availabe for DVWA on working Server.

### Open new Home Terminal 3

```ruby
mysql -u dvwa -pp@ssw0rd
```

### Return to Home Terminal 1

```ruby
sudo su
```

```ruby
cd /etc/php
```

```ruby
cd 8.1
```

```ruby
cd apache2
```

```ruby
vim php.ini
```

Type the Following as soon as the file opens: /allow_url_include

Then change the it from Off to On

Now type the following to quit Vim Editor: :wq

Now continue in the terminal

```ruby
apt update
```

```ruby
apt install php-gd
```

```ruby
chown www-data /var/www/html/hackable/uploads/
```

```ruby
chown 777 /var/www/html/hackable/uploads/
```

```ruby
chown www-data /var/www/html/DVWA/external/phpids/0.6/lib/IDS/tmp/phpids_log.txt
```

```ruby
chown www-data /var/www/html/DVWA/config
```

```ruby
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
