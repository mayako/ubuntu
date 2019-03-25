# Configuración

## Instalación

### Menu de Booteo

Si no aparece el menu de booteo (grub), ejecutar desde el Live Desktop:
```bash
sudo apt-get install grub
```

### Pantalla Negra
```
sudo gedit /etc/default/grub
GRUB_GFXPAYLOAD_LINUX="auto"
sudo update-grub
```

### Brillo
```bash
sudo add-apt-repository ppa:apandada1/brightness-controller 
sudo apt-get update 
sudo apt-get install brightness-controller
```
::: tip
Para Ubuntu 14.04 ya trae incluido el balance de brillo.
:::

### Guardado de Contraseñas
Cada vez que inicies un programa que use una contraseña, te pedirá acceso al depósito de contraseñas, para evitar esto, seguir lo siguientes pasos: 

1. Contraseñas y claves
2. Depósito de claves predeterminados o Contraseñas > Inicio de sesión (click derecho)
3. Cambiar contraseña
4. Ingresar contraseña actual
5. Nueva contraseña en blanco


### Impresora
```bash
sudo apt-get install printer-driver-escpr
```
::: warning
Solo ha funcionado en Ubuntu 14.04
:::

### Cycle windows
Permite maximizar/cambiar entre ventanas con el scroll del mouse.
```bash
gsettings set org.gnome.shell.extensions.dash-to-dock scroll-action 'cycle-windows'
```

### Install .tar.gz
```bash
cd Downloads
sudo cp dropbox-lnx.x86_64-1.5.36.tar.gz /opt/
cd /opt/
sudo tar -xvf dropbox-lnx.x86_64-1.5.36.tar.gz
sudo rm -rf dropbox-lnx.x86_64-1.5.36.tar.gz
```
#### Agregarlos al path
```bash
sudo chmod 777 .dropbox-dist/
sudo ln -s /opt/.dropbox-dist/ /usr/bin/dropbox
```

## Centro de software de Ubuntu

- [Chrome](https://www.google.com/chrome/browser/desktop/) (Chromium, Opera o Firefox)
- [Sublime Text](http://www.sublimetext.com/) - `subl`
- [MySQL Workbench](http://dev.mysql.com/downloads/workbench/)

## [jDownloader 2](http://jdownloader.org/download/offline)
```bash
sh JD2Setup_x64.sh
```
::: tip Deshabilitar la descarga en subcarpetas
Opciones > Empaquetador > Deshabilitar: Regla predefinida: Crear una subcarpeta con el nombre del Paquete
:::

## Visual Studio Code
```bash
sudo apt-get install code
```

### Numix Bar Icon
Cambiar todas las claves `Icon=code` a `Icon=vscode` en:
```bash
sudo gedit /usr/share/applications/code.desktop
```
::: tip
En Ubuntu 14.04 es necesario reiniciar la sesión, en 18.04 ya no es necesario.
:::

### [Fira Code](https://github.com/tonsky/FiraCode)
```bash
mv ~/path/to/FiraCode/ttf/*.ttf ~/.fonts
```
#### [User Settings](https://github.com/tonsky/FiraCode/wiki/VS-Code-Instructions)
```json
{
	"editor.fontFamily": "Fira Code",
	"editor.fontLigatures": true
}
```
### Editar PHP Language
```bash
sudo gedit /usr/share/code/resources/app/extensions/php/syntaxes/php.tmLanguage.json
```
#### [Theme: PHP: Clases en CamelCase no se colorean.](https://github.com/Microsoft/vscode/issues/44032#issuecomment-367552471)
```json
{
	"match": "([A-Za-z_\\x{7f}-\\x{7fffffff}\\\\][A_Za-z0-9_\\x{7f}-\\x{7fffffff}\\\\]*)(?=\\s*::)",
}
```

#### Theme: PHP: Clase despues de instanceof
```json
{
	"end": "(?=[^\\\\$A-Za-z0-9_\\x{7f}-\\x{7fffffff}])",
}
```

## Unity Tweak Tool
```bash
sudo apt-get install unity-tweak-tool
```

## [Numix Theme](https://itsfoss.com/install-numix-ubuntu/)
```bash
sudo add-apt-repository ppa:numix/ppa
sudo apt-get update
sudo apt-get install numix-gtk-theme numix-icon-theme-circle
```
#### Iconos
```
cd /usr/share/icons/Numix/64/places
```

## SMPlayer
```bash
sudo apt-get install smplayer
```

## Skype
```bash
sudo apt-get install skype
```
::: warning Requiere habilitar paquetes de Socio Canonical
Configuración del Sistema > Software y actualizaciones > Otro Software > Socio de Canonical
:::
## 7zip
```bash
sudo apt-get install p7zip p7zip-rar
```


## Postman
```bash
wget https://dl.pstmn.io/download/latest/linux64 -O postman.tar.gz
sudo tar -xzf postman.tar.gz -C /opt
rm postman.tar.gz
sudo ln -s /opt/Postman/Postman /usr/bin/postman
```

## Git
```bash
sudo apt-add-repository ppa:git-core/ppa
sudo apt-get update
sudo apt-get install git
```

## [ZSH](http://ohmyz.sh/)
```bash
sudo apt-get install zsh
sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```
::: tip
- Necesitas Git
- Necesitras cUrl
:::


## Terminator
``` bash
sudo apt-get install terminator
```

## Ruby
```bash
sudo apt-get install ruby
ruby --version
```

#### Lista de Gemas instaladas
```bash
gem list
```

### Rails
```bash
sudo apt-get install rails
# ó
sudo gem install rails
```
::: danger
Si marca un error de sqlite3 ejecutar:
```bash
apt-get install libsqlite3-dev
```
:::
::: danger
Si marca error con la gema Nokogiri :
```bash
# See http://www.nokogiri.org/tutorials/installing_nokogiri.html#ubuntu___debian
sudo apt-get install build-essential patch
sudo apt-get install ruby-dev zlib1g-dev liblzma-dev
```
:::

## Python
```bash
python --version
```
::: tip 
Python estan instalado por default.
:::

## [NodeJS](https://nodejs.org/es/download/package-manager/)
```bash
curl -sL https://deb.nodesource.com/setup_10.x | sudo -E bash -
sudo apt-get install -y nodejs
node -v 
sudo apt-get install npm
```

## [Yarn](https://yarnpkg.com/lang/en/docs/install/#debian-stable)
```bash
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
sudo apt-get update 
sudo apt-get install yarn
yarn -v
```


### Angular
```bash
sudo npm install -g @angular/cli@1.7.4
ng --version
ng new my-app
ng server
```

## [MySQL](https://www.digitalocean.com/community/tutorials/how-to-install-mysql-on-ubuntu-18-04)
```bash
sudo apt-get install mysql-server
```

##  [MariaDB](https://www.vultr.com/docs/install-mariadb-on-ubuntu-14-04)
```
sudo apt-get install mariadb-server
mysql -u root -p
```
::: warning
No tolera campos tipo JSON
:::

## Apache2
```bash
sudo apt-get install apache2
sudo apt-get update
sudo apt-get install libapache2-mod-php5 php5-mysqlnd
sudo service apache2 restart
```

### `php.ini`
 ```bash
sudo gedit /etc/php/{version}/apache2/php.ini
 # error_reporting = E_ALL & ~E_NOTICE & ~E_STRICT & ~E_WARNING
 # display_errors = On
 # short_open_tag = On
 ```
 
## PHP
```bash
sudo add-apt-repository ppa:ondrej/php
sudo apt-get install php
```
::: tip Extensiones:
```bash
sudo apt-get install php-xml php-mbstring
```
:::
::: danger
La libreria **php7.0-snmp** causa una lista de "errores" al momento de ejecutar el comando **php**.
:::

 ### `php.ini`
 ```bash
 php --ini # Muestra la ubicacion de php.ini
 # error_reporting = E_ALL & ~E_NOTICE & ~E_STRICT & ~E_WARNING
 # display_errors = On
 # short_open_tag = On
 ```
### [Composer](https://getcomposer.org/download/)
Decarga y agrega a `$PATH`
```bash
curl -sS https://getcomposer.org/installer | sudo php -- --install-dir=/usr/local/bin --filename=composer
```
### Laravel
```bash
composer global require "laravel/installer"
```
Si no esta disponible en la linea de comandos
```bash
export PATH="$PATH:$HOME/.composer/vendor/bin"
```


### Memcached

``` bash
sudo apt-get install php-memcached memcached
```


## Go :poop:
```bash
sudo apt-get install -y golang-go
go version
```

## [Google Cloud SDK](https://cloud.google.com/sdk/downloads?hl=es)
```bash
curl https://sdk.cloud.google.com | bash
exec -l $SHELL // reinicia el shell
gcloud init
```