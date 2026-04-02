# Felisiaeaa
COMMAND PUTTY

Command Putty for UKK

apt update
apt install mariadb-server -y
apt install apache2 -y
apt install php php-{cli,mysql,gd,xml,curl,mbstring,intl,zip,soap,bcmath} -y (web)
nano /etc/mysql/mariadb.conf.d/50-server.cnf (db)
systemctl restart mariadb (db)
mysql (db)
CREATE DATABASE moodle DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
CREATE USER 'felis'@'%' IDENTIFIED BY '11111111';
GRANT ALL PRIVILEGES ON moodle.* TO 'felis'@'%';
FLUSH PRIVILEGES;
EXIT;
cd /var/www/html/ (web)
wget https://download.moodle.org/download.php/direct/stable405/moodle-latest-405.tgz
tar zxvf moodle-latest-405.tgz
mkdir /var/www/moodledata 
chown -R www-data:www-data /var/www/moodledata/
chmod -R 777 /var/www/moodledata/
chown -R www-data:www-data moodle
chmod -R 777 moodle
nano /etc/php/8.3/apache2/php.ini
systemctl restart apache2
nano /var/www/html/moodle/config.php
($CFG-> wwwroot = 'http://' . $_SERVER['HTTP_HOST'] .'/moodle';)
