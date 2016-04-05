#### INSTALAÇÃO DE SERVIDOR OTIMIZADO PARA WordPress


setxkbmap -model abnt2 -layout br

#### PASSO 1
``` sh
sudo -i
cd /
apt-get update && apt-get upgrade && apt-get dist-upgrade
```


#### PASSO 2

- wget -qO ee rt.cx/ee && sudo bash ee


#### PASSO 3

- nano /etc/ee/ee.conf

##### [mysql]

Ask for MySQL db name while site creation <br>
db-name = **True**

Ask for MySQL user name while site creation <br>
db-user =  **True**

##### [wordpress]

Ask for WordPress prefix while site creation <br>
prefix = **True**

User name for WordPress sites <br>
user = **useradmin**

Password for WordPress sites <br>
password = **senhaadmin**

EMail for WordPress sites <br>
email = **emailadmin**


#### PASSO 4

- ee site create MINHALOJA.com.br --wpfc


#### PASSO 5

- nano /var/www/MINHALOJA.com.br/wp-config.php

  ``` php
  define( 'WP_MEMORY_LIMIT', '128M' );
  define ( 'AUTOMATIC_UPDATER_DISABLED', true );
  ```

#### BÔNUS (PHPMyAdmin)

- ee secure --auth

- ee stack install --phpmyadmin

- nano /etc/mysql/conf.d/my.cnf

``` html
http://www.MINHALOJA.com.br/pma
```


##### 

sudo apt-get install proftpd

Pressione “Enter” para confirmar o tipo padrão “autônomo”

nano /etc/proftpd/proftpd.conf

**Agora procure pelo item “ServerName”, por volta da linha 15, e altere o nome “Debian” para o nome que quiser dar ao seu sevidor de FTP

“User” aproximadamente na linha 68. mudar por ftp

sudo passwd ftp

sudo addgroup ftp

sudo addgroup ftp ftp

nano /etc/passwd

ftp:x:118:65534::/var/www/w1:/bin/bash

sudo chmod 777 /var/www/w1

sudo /etc/init.d/proftpd restart

sudo /etc/init.d/proftpd status

