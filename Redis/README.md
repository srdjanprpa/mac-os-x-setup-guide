## Redis

Ako koristite Homebrew

        brew install redis

Ako ne koristite Homebrew, skinite redis sa njihovog sajta [Redis.io](http://redis.io), ja sam skinuo redis u Downloads folder na Mac-u.
- Prvo ćemo otpakovati redis
- Pokrenućemo make test da se uverimo da Redis može da se instalira na kompljuteru
- Ako su svi testovi prošli, pokrenućemo instalaciju make

        $ cd ~/Downloads/redis-3.0.7.tar.gz
        $ tar -zxvf redis-3.0.7.tar.gz
        $ make test
        $ make

Pomeramo dva direktorijuma u /usr/bin folder, za ovu komandu moramo koristiti sudo user-a.

        $ sudo mv src/redis-server /usr/binm
        $ sudo mv src/redis-cli /usr/bin

Pravimo ne vidljiv redis foldera u home folderu i u njemu pravimo redis.conf fajl.

        $ mkdir ~/.redis
        $ touch ~/.redis/redis.conf

Pokretanje redis servera

        $ redis-server
