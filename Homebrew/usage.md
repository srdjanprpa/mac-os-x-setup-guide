## Kako se koristi Homebrew

Za instalaciju nekog paketa u terminalu otkucamo

        $ brew install <paket>

Za updetjovanje Homebrew-a otkucamo

        $ brew update

U slucaju da dobijete neku gresku zbog nekog bug-a, ako se to desi probajte sledece

        $ cd /usr/local
        $ git fetch origin
        $ git reset --hard origin/master

Da vidite da li neki paket ima novu verziju za azuriranje

        $ brew outdated

Homebrew cuva stare verzije instaliranih paketa u slucaju da hocete da vratite neku staru verziju. Ako zelite da izbrisete stare verzije paketa otkucajte

        $ brew cleanup

Za updetjovanje nekog paketa koji smo instalirali preko Homebrew

        $ brew update <paket>

Da pogledamo listu instaliranih paketa preko Homebrew

        $ brew list --versions
