## CONFIGURANDO um AMBIENTE de DESENVOLVIMENTO LARAVEL no LINUX
https://www.youtube.com/watch?v=m7ULdRiMd-w&t=324s


## 1.0 Instalar PHP
https://computingforgeeks.com/how-to-install-php-8-2-on-ubuntu/#google_vignette

```bash
sudo apt update
sudo apt install -y lsb-release gnupg2 ca-certificates apt-transport-https software-properties-common
```
```bash
sudo add-apt-repository ppa:ondrej/php
```
```bash
sudo apt install php8.2 -y
```

## 2.0 Instalar composer
https://getcomposer.org/download/


```bash
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
php -r "if (hash_file('sha384', 'composer-setup.php') === 'dac665fdc30fdd8ec78b38b9800061b4150413ff2e3b6f88543c636f7cd84f6db9189d43a81e5503cda447da73c7e5b6') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
php composer-setup.php
php -r "unlink('composer-setup.php');"
```
```bash
sudo mv composer.phar /usr/local/bin/composer
```

## 3.0 Instalar nvm
https://www.treinaweb.com.br/blog/instalando-e-gerenciando-varias-versoes-do-node-js-com-nvm

```bash
sudo apt install curl -y 
curl https://raw.githubusercontent.com/creationix/nvm/master/install.sh | bash
```
```bash
source ~/.bashrc
```
```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.34.0/install.sh | bash
```
```bash
source ~/.bashrc
```
```bash
nvm install node
```

## 4.0 Instalar valet-linux
https://cpriego.github.io/valet-linux/

```bash
sudo systemctl stop apache2 && sudo systemctl disable apache2
```
```bash
sudo apt install network-manager libnss3-tools jq xsel -y
```
```bash
sudo apt install php8.2-mbstring php8.2-cli php8.2-curl php8.2-xml php8.2-zip php8.2-mysql php8.2-pgsql php8.2-sqlite3 php8.2-gd -y
```
```bash
composer global require cpriego/valet-linux
```
```bash
nano .bashrc
```
## Inserir no final do texto

```bash
export PATH=$PATH:$HOME/.config/composer/vendor/bin/
```
```bash
source ~/.bashrc
```

```bash
valet install && valet restart && valet paths && mkdir code && cd code && valet park && valet paths
```

## 5.0 Instalar docker
https://computingforgeeks.com/install-docker-docker-compose-on-linux-mint/


```bash
sudo apt update
sudo apt -y install apt-transport-https ca-certificates curl software-properties-common
sudo apt -y remove docker docker-engine docker.io containerd runc

```
```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```
```bash
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu jammy stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

```
```bash
cat /etc/apt/sources.list.d/docker.list
```


## 5.1 Install Docker Engine e Docker Compose
https://docs.docker.com/engine/install/ubuntu/

```bash
sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y

```
```bash
sudo usermod -aG docker $USER
```
```bash
newgrp docker
```
```bash
docker version
```
```bash
sudo apt-get remove docker docker-engine docker.io containerd runc
```
```bash
sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

```
```bash
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update

```
```bash
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y
```
```bash
docker ps
```


## 6.0 Instalar takeout
https://github.com/tighten/takeout

```bash
composer global require tightenco/takeout
```
```bash
takeout enable mysql
```
```bash
password
```


## 7.0 instalar laravel global
```bash
composer global require laravel/installer
```


## 8.0 Terminal zsh
https://dev.to/henriquemsimoes/instalando-e-configurando-zsh-e-oh-my-zsh-4bem

```bash
sudo apt install zsh -y
```
```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)" -y
```
```bash
git clone https://github.com/spaceship-prompt/spaceship-prompt.git "$ZSH_CUSTOM/themes/spaceship-prompt" --depth=1

ln -s "$ZSH_CUSTOM/themes/spaceship-prompt/spaceship.zsh-theme" "$ZSH_CUSTOM/themes/spaceship.zsh-theme"

```
```bash
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```
```bash
source ~/.zshrc
```
```bash
nano ~/.zshrc
```
```bash
# If you come from bash you might have to change your $PATH.
# export PATH=$HOME/bin:/usr/local/bin:$PATH

# Path to your oh-my-zsh installation.
export ZSH="$HOME/.oh-my-zsh"

# Set name of the theme to load --- if set to "random", it will
# load a random theme each time oh-my-zsh is loaded, in which case,
# to know which specific one was loaded, run: echo $RANDOM_THEME
# See https://github.com/ohmyzsh/ohmyzsh/wiki/Themes
ZSH_THEME="spaceship"

# Set list of themes to pick from when loading at random
# Setting this variable when ZSH_THEME=random will cause zsh to load
# a theme from this variable instead of looking in $ZSH/themes/
# If set to an empty array, this variable will have no effect.
# ZSH_THEME_RANDOM_CANDIDATES=( "robbyrussell" "agnoster" )

# Uncomment the following line to use case-sensitive completion.
# CASE_SENSITIVE="true"

# Uncomment the following line to use hyphen-insensitive completion.
# Case-sensitive completion must be off. _ and - will be interchangeable.
# HYPHEN_INSENSITIVE="true"

# Uncomment one of the following lines to change the auto-update behavior
# zstyle ':omz:update' mode disabled  # disable automatic updates
# zstyle ':omz:update' mode auto      # update automatically without asking
# zstyle ':omz:update' mode reminder  # just remind me to update when it's time

# Uncomment the following line to change how often to auto-update (in days).
# zstyle ':omz:update' frequency 13

# Uncomment the following line if pasting URLs and other text is messed up.
# DISABLE_MAGIC_FUNCTIONS="true"

# Uncomment the following line to disable colors in ls.
# DISABLE_LS_COLORS="true"

# Uncomment the following line to disable auto-setting terminal title.
# DISABLE_AUTO_TITLE="true"

# Uncomment the following line to enable command auto-correction.
# ENABLE_CORRECTION="true"

# Uncomment the following line to display red dots whilst waiting for completion.
# You can also set it to another string to have that shown instead of the default red dots.
# e.g. COMPLETION_WAITING_DOTS="%F{yellow}waiting...%f"
# Caution: this setting can cause issues with multiline prompts in zsh < 5.7.1 (see #5765)
# COMPLETION_WAITING_DOTS="true"

# Uncomment the following line if you want to disable marking untracked files
# under VCS as dirty. This makes repository status check for large repositories
# much, much faster.
# DISABLE_UNTRACKED_FILES_DIRTY="true"

# Uncomment the following line if you want to change the command execution time
# stamp shown in the history command output.
# You can set one of the optional three formats:
# "mm/dd/yyyy"|"dd.mm.yyyy"|"yyyy-mm-dd"
# or set a custom format using the strftime function format specifications,
# see 'man strftime' for details.
# HIST_STAMPS="mm/dd/yyyy"

# Would you like to use another custom folder than $ZSH/custom?
# ZSH_CUSTOM=/path/to/new-custom-folder

# Which plugins would you like to load?
# Standard plugins can be found in $ZSH/plugins/
# Custom plugins may be added to $ZSH_CUSTOM/plugins/
# Example format: plugins=(rails git textmate ruby lighthouse)
# Add wisely, as too many plugins slow down shell startup.
plugins=(git zsh-autosuggestions zsh-syntax-highlighting)

source $ZSH/oh-my-zsh.sh

# User configuration

# export MANPATH="/usr/local/man:$MANPATH"

# You may need to manually set your language environment
# export LANG=en_US.UTF-8

# Preferred editor for local and remote sessions
# if [[ -n $SSH_CONNECTION ]]; then
#   export EDITOR='vim'
# else
#   export EDITOR='mvim'
# fi

# Compilation flags
# export ARCHFLAGS="-arch x86_64"

# Set personal aliases, overriding those provided by oh-my-zsh libs,
# plugins, and themes. Aliases can be placed here, though oh-my-zsh
# users are encouraged to define aliases within the ZSH_CUSTOM folder.
# For a full list of active aliases, run `alias`.
#
# Example aliases
# alias zshconfig="mate ~/.zshrc"
# alias ohmyzsh="mate ~/.oh-my-zsh"

alias pa="php artisan"
alias cc="php artisan config:clear && php artisan route:clear && php artisan view:clear && php artisan config:cache && php artisan route:cache && php artisan view:cache"
alias nd="bun run dev"
alias nb="bun run build"
alias env="cp .env.example .env"
alias rl="php artisan route:list --except-vendor"
alias op="php artisan optimize:clear"

alias ga="git add ."
alias gs="git status"
alias gp="git pull"
alias gm="git commit -m"
alias gc="git clone"
alias wip="git add .;git commit -m 'wip' > /dev/null;git push"

alias db="php artisan migrate:fresh --seed"
alias ms="php artisan migrate:status"
alias m="php artisan migrate"
alias za="nano ~/.zshrc"
alias sl="php artisan storage:link"
alias tl="takeout list"
alias te="takeout enable"
alias ts="takeout start"
alias td="takeout disable --all"
alias tdb="takeout enable mariadb"
alias pc="gp && nb && cc"  
alias cn="composer install && npm install"
alias tp="pa test --parallel"
alias tdd="./vendor/bin/pest --dirty"
alias t="pa test"
alias tinker="pa tinker"
alias key="pa key:generate"
alias pint="./vendor/bin/pint"
alias stan="./vendor/bin/phpstan analyse"
alias gg="ga && gm"
alias gne="git config --global user.name ‘LeandroAndrade’; git config --global user.email profeleandro@outlook.com"
alias sqlite="touch database/database.sqlite"
alias pld="composer require pestphp/pest --dev --with-all-dependencies && composer require nunomaduro/larastan:^2.0 --dev && composer require barryvdh/laravel-debugbar --dev"
alias debugbar="composer require barryvdh/laravel-debugbar --dev"
alias model="pa make:model"
alias live="pa make:livewire"
alias log="composer require opcodesio/log-viewer && php artisan log-viewer:publish"
alias ms="php artisan migrate:status"
alias mr="php artisan migrate:rollback --step=1"
alias heroicons="composer require blade-ui-kit/blade-heroicons"
alias lang="php artisan lang:publish"
alias form="pa livewire:form"
alias v="pa make:volt"
alias pg="php artisan powergrid:create"

alias ci="composer install"
alias cu="composer update"
alias ni="bun install"
alias nu="bun update"

#plugins
alias debugbar="composer require barryvdh/laravel-debugbar --dev"
alias dompdf="composer require barryvdh/laravel-dompdf && pa vendor:publish --provider='Barryvdh\DomPDF\ServiceProvider'"
alias iseed="composer require orangehill/iseed"
alias icon="composer require blade-ui-kit/blade-heroicons"
alias excel="composer require maatwebsite/excel"
alias bi="curl -fsSL https://bun.sh/install | bash"
alias volt="composer require livewire/volt && php artisan volt:install"

export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion

export PATH=$PATH:$HOME/.config/composer/vendor/bin/

```

## 9.0 Instalar Bun
```bash
curl -fsSL https://bun.sh/install | bash
```

## 10.0 Aplicativos 
```bash
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
```
```bash
sudo dpkg -i google-chrome-stable_current_amd64.deb
```
```bash
wget https://dbeaver.io/files/dbeaver-ce_latest_amd64.deb
```
```bash
https://www.microsoft.com/pt-br/edge/download
```
```bash
https://code.visualstudio.com/docs/?dv=linux64_deb
```
```bash
https://termius.com/download/linux
```






# Licença

Este projeto está licenciado sob a licença MIT. Consulte o arquivo [LICENSE](./LICENSE.md) para obter mais detalhes.

