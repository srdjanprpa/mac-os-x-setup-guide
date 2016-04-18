## Apache

#### Podešavanje Apacha

Kreiranje config fajla u users folderu

        $ cd /etc/apache2/users
        sudo nano accountname.conf

        //U config fajls sačuvajte
        <Directory "/Users/accountname/Sites/">
          AllowOverride All
          Options Indexes MultiViews FollowSymLinks
          Require all granted
        </Directory>

        //Podesite chmod accountname.conf na 644
        sudo chmod 644 accountname.conf

Uključivanje modula u httpd.conf fajlu

        $ cd /etc/apache2/

        //Pravljenje backup/a httpd.conf fajla
        $  sudo cp httpd.conf httpd.conf.bak

        sudo nano httpd.conf

        //Izbrisite tarabu (#) na sledećim linijama koda
        LoadModule authz_host_module libexec/apache2/mod_authz_host.so
        LoadModule authz_core_module libexec/apache2/mod_authz_core.so
        LoadModule userdir_module libexec/apache2/mod_userdir.so
        LoadModule vhost_alias_module libexec/apache2/mod_vhost_alias.so
        LoadModule rewrite_module libexec/apache2/mod_rewrite.so
        LoadModule php5_module libexec/apache2/libphp5.so
        Include /private/etc/apache2/extra/httpd-userdir.conf
        Include /private/etc/apache2/extra/httpd-vhosts.conf

Dodavanje user config fajla

        $  cd /etc/apache2/extra
        $  sudo cp httpd-userdir.conf httpd-userdir.conf.bak

        //Izbrisite tarabu (#) na sledećim liniji koda i umesto zvezdice (*) unesite ime vaseg naloga
        Include /private/etc/apache2/users/*.conf

Restartovanje Apacha

        $ sudo apachectl restart

Provera da li radi apachectl u browseru idite na sledeci link http://localhost/~accountname/

#### Konfigurisanje Apacha

Pravljenje virutal host-a

        $ cd /etc/apache2/extra

        //Pravljenje backup-a httpd-vhosts.conf
        $ sudo cp httpd-vhosts.conf httpd-vhosts.conf.bak

        $ sudo nano httpd-vhosts.conf

        <VirtualHost *:80>
            ServerAdmin webmaster@domen.dev
            DocumentRoot "/Users/accountname/Sites/domen.dev"
            ServerName domen.dev
            ServerAlias www.domen.dev
            ErrorLog "/private/var/log/apache2/domen.dev-error_log"
            CustomLog "/private/var/log/apache2/domen.dev-access_log" common
        </VirtualHost>


##### Pravljenje host-a

        $ sudo nano /etc/hosts

        127.0.0.1 http://www.domain.dev www.domain.dev  http://domain.dev domain.dev

        //Izmene sačuvati i restartovati apache
        $ sudo apachectl restart

##### PHP greska Is Writable by PHP

U slucaju da dobijete gresku da Is Writable by PHP FAILD

        $ sudo nano /private/etc/apache2/httpd.conf

        //Pronađite i promenite sledeće dve linije koda
        User _www
        Group _www

        User accountname
        Group staff

        //Restartujte apach
        sudo apachectl restart
