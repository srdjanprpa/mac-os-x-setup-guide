## MongoDB

Skinuti MongoDB sa sajta www.mongodb.org ili pomocu shell-a, u terminalu ukucajte sledece

        curl -O https://fastdl.mongodb.org/osx/mongodb-osx-x86_64-3.2.4.tgz

Otpakujte mongodb

        tar -zxvf mongodb-osx-x86_64-3.2.4.tgz

Prekopirajte mongodb u /usr/local/mongodb odakle ce se pokretati mongodb

        sudo mv mongodb-osx-x86_64-3.2.4 /usr/local/mongodb

Napraviti data direktorijum za MongoDB, uobičajno MongoDB je smešten u /data/db folder, treba da napravite folder i dodate korisniku dozvole

        sudo mkdir -p /data/db
        $ whoami
        MacUser
        $ sudo chown MacUser /data/db

Dodavanje mongodb/bin u $PATH

Naparavite ~/.bash_profile i dodelite /usr/local/mongodb/bin u $PATH promenljivu da bi mogli da imate pristup Mongo lakse.

        $ cd ~
        $ pwd
        /Users/MacUser
        $ nano .zshrc

        // Zamenite export PATH="/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin" sa:
        export MONGO_PATH="/usr/local/mongodb/bin"
        export PATH="$MONGO_PATH:/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin"


        // Restartujte terminal ili $ reload ako ste ukljucili .zshrc config fajl.
        $ mongo -version
        MongoDB shell version: 3.2.4


Pokretanje MongoDB i Mongo shell-a

        //Start Mongo server
        $ mongod

        //Start Mongo Shell
        $ mongo
