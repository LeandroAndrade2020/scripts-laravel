## CONFIGURANDO um AMBIENTE de DESENVOLVIMENTO LARAVEL no LINUX


## 1.0 Instalar PHP

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
sudo install node
```

## 4.0 Instalar valet-linux
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
##Inserir no final do texto

```bash
export PATH=$PATH:$HOME/.config/composer/vendor/bin/
```
```bash
source ~/.bashrc
```bash
valet install && valet restart && valet paths && mkdir code && cd code && valet park && valet paths
```

## 5.0 Instalar docker
```bash
sudo systemctl stop apache2 && sudo systemctl disable apache2
```
```bash
cd public_html/domains/patrimonios.educacaocaraguatatuba.com.br
```
```bash
cd public_html/domains/quadros.educacaocaraguatatuba.com.br
```
```bash
cd public_html/domains/votacao.educacaocaraguatatuba.com.br
```
## 4.0 Instalar valet-linux
```bash
sudo systemctl stop apache2 && sudo systemctl disable apache2
```
```bash
cd public_html/domains/patrimonios.educacaocaraguatatuba.com.br
```
```bash
cd public_html/domains/quadros.educacaocaraguatatuba.com.br
```
```bash
cd public_html/domains/votacao.educacaocaraguatatuba.com.br
```
## 4.0 Instalar valet-linux
```bash
sudo systemctl stop apache2 && sudo systemctl disable apache2
```
```bash
cd public_html/domains/patrimonios.educacaocaraguatatuba.com.br
```
```bash
cd public_html/domains/quadros.educacaocaraguatatuba.com.br
```
```bash
cd public_html/domains/votacao.educacaocaraguatatuba.com.br
```
## 4.0 Instalar valet-linux
```bash
sudo systemctl stop apache2 && sudo systemctl disable apache2
```
```bash
cd public_html/domains/patrimonios.educacaocaraguatatuba.com.br
```
```bash
cd public_html/domains/quadros.educacaocaraguatatuba.com.br
```
```bash
cd public_html/domains/votacao.educacaocaraguatatuba.com.br
```
## 4.0 Instalar valet-linux
```bash
sudo systemctl stop apache2 && sudo systemctl disable apache2
```
```bash
cd public_html/domains/patrimonios.educacaocaraguatatuba.com.br
```
```bash
cd public_html/domains/quadros.educacaocaraguatatuba.com.br
```
```bash
cd public_html/domains/votacao.educacaocaraguatatuba.com.br
```






# Licença

Este projeto está licenciado sob a licença MIT. Consulte o arquivo [LICENSE](./LICENSE.md) para obter mais detalhes.

