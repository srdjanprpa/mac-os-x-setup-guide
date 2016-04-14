## Zsh

Instalacija zsh koju nudi oh-my-zsh

Ako koristite Homebrew

        $ brew install zsh zsh-completions

Ako ne koristite homebrew, instalirajte preko shell-a

        $ sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

#### Podešavanja zsh shell-a

Podešavanja zsh shell-a

        $ nano ~/.zshrc

        //Podesiti ZSH_THEME na
        ZSH_THEME="apple"

        //Dodati na dnu fajla aliase
        //Pokretanje novog config fajla
        alias reload=". ~/.zshrc && echo 'ZSH config reloaded from ~/.zshrc'"

        //Editovanje zsh configa preko Atom aplikacije
        alias zshconf='atom ~/.zshrc'
