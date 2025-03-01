## CONFIGURANDO um AMBIENTE de DESENVOLVIMENTO LARAVEL no LINUX
https://www.youtube.com/watch?v=m7ULdRiMd-w&t=324s


## 1.0 Instalar PHP e Instalar composer e Instalar nvm e Instalar valet-linux
https://computingforgeeks.com/how-to-install-php-8-2-on-ubuntu/#google_vignette

https://ubuntuhandbook.org/index.php/2024/11/install-or-upgrade-to-php-8-4-in-ubuntu-24-04-22-04/

https://www.treinaweb.com.br/blog/instalando-e-gerenciando-varias-versoes-do-node-js-com-nvm
https://cpriego.github.io/valet-linux/

## PHP8.2
```bash
sudo apt update && sudo apt install -y lsb-release gnupg2 ca-certificates apt-transport-https software-properties-common && sudo add-apt-repository ppa:ondrej/php && sudo apt install php8.2 -y && php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
php -r "if (hash_file('sha384', 'composer-setup.php') === 'dac665fdc30fdd8ec78b38b9800061b4150413ff2e3b6f88543c636f7cd84f6db9189d43a81e5503cda447da73c7e5b6') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;" 
php composer-setup.php
php -r "unlink('composer-setup.php');"  && sudo mv composer.phar /usr/local/bin/composer &&
sudo apt install curl -y 
curl https://raw.githubusercontent.com/creationix/nvm/master/install.sh | bash && source ~/.bashrc && curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.34.0/install.sh | bash && source ~/.bashrc && nvm install node &&
sudo systemctl stop apache2 && sudo systemctl disable apache2 && sudo apt install network-manager libnss3-tools jq xsel -y && sudo apt install php8.2-mbstring php8.2-cli php8.2-curl php8.2-xml php8.2-zip php8.2-mysql php8.2-pgsql php8.2-sqlite3 php8.2-gd -y && composer global require cpriego/valet-linux && nano .bashrc
```

## PHP8.4
```bash
sudo apt update && sudo apt install -y lsb-release gnupg2 ca-certificates apt-transport-https software-properties-common && sudo add-apt-repository ppa:ondrej/php && sudo apt install php8.4 -y && php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
php -r "if (hash_file('sha384', 'composer-setup.php') === 'dac665fdc30fdd8ec78b38b9800061b4150413ff2e3b6f88543c636f7cd84f6db9189d43a81e5503cda447da73c7e5b6') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;" 
php composer-setup.php
php -r "unlink('composer-setup.php');"  && sudo mv composer.phar /usr/local/bin/composer &&
sudo apt install curl -y 
curl https://raw.githubusercontent.com/creationix/nvm/master/install.sh | bash && source ~/.bashrc && curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.34.0/install.sh | bash && source ~/.bashrc && nvm install node &&
sudo systemctl stop apache2 && sudo systemctl disable apache2 && sudo apt install network-manager libnss3-tools jq xsel -y && sudo apt install php8.4-mbstring php8.4-cli php8.4-curl php8.4-xml php8.4-zip php8.4-mysql php8.4-pgsql php8.4-sqlite3 php8.4-gd -y && composer global require cpriego/valet-linux && nano .bashrc
```
## Inserir no final do texto

```bash
export PATH=$PATH:$HOME/.config/composer/vendor/bin/
```
## 2.0 instalar valet e instalar laravel global e Terminal zsh
https://dev.to/henriquemsimoes/instalando-e-configurando-zsh-e-oh-my-zsh-4bem
```bash
source ~/.bashrc && valet install && valet restart && valet paths && mkdir code && cd code && valet park && valet paths && composer global require laravel/installer && sudo apt install zsh -y && sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)" -y
```

```bash
git clone https://github.com/spaceship-prompt/spaceship-prompt.git "$ZSH_CUSTOM/themes/spaceship-prompt" --depth=1

ln -s "$ZSH_CUSTOM/themes/spaceship-prompt/spaceship.zsh-theme" "$ZSH_CUSTOM/themes/spaceship.zsh-theme"

git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```
```bash
source ~/.zshrc && nano ~/.zshrc
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
alias control="pa make:controller"
alias live="pa make:livewire"
alias log="composer require opcodesio/log-viewer && php artisan log-viewer:publish"
alias ms="php artisan migrate:status"
alias mr="php artisan migrate:rollback --step=1"
alias heroicons="composer require blade-ui-kit/blade-heroicons"
alias lang="php artisan lang:publish"
alias form="pa livewire:form"
alias v="pa make:volt"
alias pg="php artisan powergrid:create"
alias ds="php artisan ds:init $(pwd)"
alias pi="pa iseed"

alias ci="composer install"
alias cu="composer update"
alias ni="bun install"
alias nu="bun update"
alias up="cu && nu && nb && cc && op && nd"
alias start="env && ci && cu && ni && nu && nb && cc && op && nd"
alias lf="rm -rf node_modules package-lock.json && npm install && npm run dev"

#plugins
alias debugbar="composer require barryvdh/laravel-debugbar --dev"
alias dompdf="composer require barryvdh/laravel-dompdf && pa vendor:publish --provider='Barryvdh\DomPDF\ServiceProvider'"
alias iseed="composer require orangehill/iseed"
alias icon="composer require blade-ui-kit/blade-heroicons"
alias excel="composer require maatwebsite/excel"
alias bi="curl -fsSL https://bun.sh/install | bash"
alias volt="composer require livewire/volt && php artisan volt:install"
alias ide="composer require --dev barryvdh/laravel-ide-helper && php artisan ide-helper:generate && php artisan ide-helper:models"

export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion

export PATH=$PATH:$HOME/.config/composer/vendor/bin/

```
```bash
source ~/.zshrc && nano ~/.zshrc
```

## 3.0 Banco de dados 

https://www.digitalocean.com/community/tutorials/how-to-install-mysql-on-ubuntu-22-04

```bash
sudo apt update && sudo apt install mysql-server && sudo systemctl start mysql && sudo systemctl enable mysql
```

```bash
sudo mysql -u root -p
```

```bash
CREATE USER 'leandro'@'localhost' IDENTIFIED BY 'PASSWORD';
```

```bash
GRANT ALL PRIVILEGES ON *.* TO 'leandro'@'localhost' WITH GRANT OPTION;
```

```bash
FLUSH PRIVILEGES;
```

Altere o método de autenticação:
No console do MySQL, altere o plugin de autenticação para mysql_native_password.
```bash
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
```
```bash
exit

```
## 4.0 Instalar Bun e DBeaver e Google Chrome
```bash
curl -fsSL https://bun.sh/install | bash && wget https://dbeaver.io/files/dbeaver-ce_latest_amd64.deb && sudo dpkg -i dbeaver-ce_latest_amd64.deb && wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb && sudo dpkg -i google-chrome-stable_current_amd64.deb
```

## 5.0 Aplicativos 
```bash
https://www.microsoft.com/pt-br/edge/download
```
```bash
https://code.visualstudio.com/docs/?dv=linux64_deb
```

## 5.1 PgSql

https://www.hostinger.com.br/tutoriais/instalar-postgresql-ubuntu-20-04

```bash
sudo apt install postgresql postgresql-contrib

```
```bash
sudo systemctl status postgresql

```
```bash
sudo systemctl start postgresql
sudo systemctl enable postgresql

```
```bash
sudo -i -u postgres

```
```bash
psql

```
Alterar a senha da conta postgres
```bash
ALTER USER postgres PASSWORD 'password';
```
```bash
sudo service postgresql restart
```

```bash
CREATE USER leandro WITH PASSWORD 'password';
```
```bash
ALTER USER leandro WITH SUPERUSER;
```
```bash
ALTER USER leandro WITH CREATEDB;
```
```bash
ALTER USER leandro WITH CREATEROLE;
```
```bash
ALTER USER usuario_teste WITH CREATEDB;
```

```bash
CREATE DATABASE nome_do_banco;
```

```bash
GRANT ALL PRIVILEGES ON DATABASE nome_do_banco TO leandro;

```
```bash
\q
```
```bash
exit
```
## 11.3 PgAdmin4
```bash
curl -fsS https://www.pgadmin.org/static/packages_pgadmin_org.pub | sudo gpg --dearmor -o /usr/share/keyrings/packages-pgadmin-org.gpg
```
```bash
sudo sh -c 'echo "deb [signed-by=/usr/share/keyrings/packages-pgadmin-org.gpg] https://ftp.postgresql.org/pub/pgadmin/pgadmin4/apt/$(lsb_release -cs) pgadmin4 main" > /etc/apt/sources.list.d/pgadmin4.list && apt update'
```
```bash
sudo apt install pgadmin4-desktop
```
## 11.4 Backup banco de dados no pgsql
```bash
pg_dump -U leandro -h localhost -d atribuicao_professor -F c -b -v -f atribuicao_professor.dump 
```

## 12.0 Dual boot Pop Os com Windows 11

```bash
sudo fdisk -l 
```
```bash
sudo mkdir /mnt/windows
```
```bash
sudo mount /dev/nvme0n1p1 /mnt/windows
```
```bash
sudo cp -r /mnt/windows/EFI/Microsoft /boot/efi/EFI
```
```bash
sudo ls /boot/efi/EFI
```
```bash
sudo nano /boot/efi/loader/loader.conf
```
```bash
default Pop_OS-current
timeout 5
console-mode max
```
```bash
sudo umount /mnt/windows 
```
```bash
sudo rm -rf /mnt/windows/
```
```bash
exit
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



# Licença

Este projeto está licenciado sob a licença MIT. Consulte o arquivo [LICENSE](./LICENSE.md) para obter mais detalhes.

