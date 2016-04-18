## SSH Key

Pravljenje ssh ključa

        //Napravite .ssh folder ako ne postoji u home direktorijumu
        $ mkdir -p $HOME/.ssh

        $ cd ~/.ssh

        $ ssh-keygen -t rsa

Kopiranje ssh ključa

        $ pbcopy < ~/.ssh/id_rsa.pub
