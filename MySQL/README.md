## MySQL

Instalacija MySQL baze

        $ brew install mysql

Nakon instalacije podesimo MySQL

        $ unset TMPDIR
        $ mkdir /usr/local/var
        $ mysqld -initialize --verbose --user=whoami --basedir="$(brew --prefix mysql)" --datadir=/usr/local/var/mysql --tmpdir=/tmp

Nakon podesavanja ostalo nam je da u .bashrc ili ako koristite Zsh onda u .zshrc podesite mysql export

        export MYSQL_PATH="/usr/local/mysql/bin"

#### Korišćenje MySQL

Pokretanje MySQL servera

        $ mysql.server start

Gašenje MySQL servera

        $ mysql.server stop

Konektovanje na komandu liniju mysql

        $ mysql -uroot

        //Za izlazak iz MySQL shell-a otkucati
        exit

**Info**: Po default-u MySQL ima usera root bez passworda, za setovanje passworda za root usera

        $ mysqladmin -u root password 'new-password'
