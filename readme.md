# A Basic Development Setup Guide for macOS
Last Updated on 11-05-2021
***
- [A Basic Development Setup Guide for macOS](#a-basic-development-setup-guide-for-macos)
    - [<u>Software Update</u>](#software-update)
    - [<u>iTerm2</u>](#iterm2)
    - [<u>Nerd Fonts</u>](#nerd-fonts)
    - [<u>Install Command Line Tools without Xcode</u>](#install-command-line-tools-without-xcode)
    - [<u>Homebrew</u>](#homebrew)
    - [<u>ZSH</u>](#zsh)
    - [<u>Oh My Zsh</u>](#oh-my-zsh)
    - [<u>Git</u>](#git)
    - [<u>SSH Keys</u>](#ssh-keys)
    - [<u>Powerlevel10k</u>](#powerlevel10k)
    - [<u>Message of the Day</u>](#message-of-the-day)
    - [<u>Homebrew Packages</u>](#homebrew-packages)
      - [tree](#tree)
      - [fzf](#fzf)
      - [ack](#ack)
      - [htop](#htop)
      - [httpd](#httpd)
      - [gcc](#gcc)
      - [mas](#mas)
      - [neofetch](#neofetch)
      - [nmap](#nmap)
      - [openSSH](#openssh)
      - [openSSL](#openssl)
      - [p7zip](#p7zip)
      - [rsync](#rsync)
      - [ssh-copy-id](#ssh-copy-id)
      - [subnetcalc](#subnetcalc)
      - [telnet](#telnet)
      - [the silver searcher](#the-silver-searcher)
      - [thefuck](#thefuck)
      - [TLDR](#tldr)
      - [tmux](#tmux)
      - [trash](#trash)
      - [unzip](#unzip)
      - [watch](#watch)
      - [wget](#wget)
      - [youtube-dl](#youtube-dl)
      - [vim](#vim)
      - [exa](#exa)
      - [autojump](#autojump)
    - [<u>Speedtest CLI by Ookla</u>](#speedtest-cli-by-ookla)
    - [<u>GPG</u>](#gpg)
    - [<u>Python</u>](#python)
    - [<u>Virtualenv</u>](#virtualenv)
    - [<u>Pipenv</u>](#pipenv)
    - [<u>Ruby</u>](#ruby)
    - [<u>RubyGems and Bundler</u>](#rubygems-and-bundler)
    - [<u>Rails</u>](#rails)
    - [<u>MySQL</u>](#mysql)
    - [<u>MySQL Workbench</u>](#mysql-workbench)
    - [<u>PostgreSQL</u>](#postgresql)
    - [<u>MongoDB</u>](#mongodb)
    - [<u>Node JS</u>](#node-js)
    - [<u>Yarn</u>](#yarn)
    - [<u>Go Lang</u>](#go-lang)
    - [<u>AWS Command Line Interface</u>](#aws-command-line-interface)
    - [<u>Boto</u>](#boto)
    - [<u>Docker</u>](#docker)
    - [<u>Java JDK 8</u>](#java-jdk-8)
    - [<u>Aircrack-ng</u>](#aircrack-ng)
    - [<u>Apache Server</u>](#apache-server)
    - [<u>PHP</u>](#php)
    - [<u>PHP-FPM with Nginx</u>](#php-fpm-with-nginx)
    - [<u>Sublime Text</u>](#sublime-text)
    - [<u>Visual Studio Code</u>](#visual-studio-code)
    - [<u>VirtualBox</u>](#virtualbox)
    - [<u>Setting up Alias</u>](#setting-up-alias)
    - [<u>Write to NTFS on macOS Catalina</u>](#write-to-ntfs-on-macos-catalina)
    - [<u>Disable macOS Gatekeeper</u>](#disable-macos-gatekeeper)
    - [<u>Spoof MAC Address</u>](#spoof-mac-address)
    - [<u>Tweaks to macOS</u>](#tweaks-to-macos)
    - [<u>Capture The Flag Tools<u>](#capture-the-flag-tools)
    - [<u>Ghidra</u>](#ghidra)
    - [<u>Metasploit Framework</u>](#metasploit-framework)
    - [<u>Recommended Firefox Browser Extensions</u>](#recommended-firefox-browser-extensions)
    - [<u>Firefox Privacy Focused Configuration</u>](#firefox-privacy-focused-configuration)
    - [<u>macOS Appearance</u>](#macos-appearance)
    - [<u>Save to Disk by Default (Not iCloud)</u>](#save-to-disk-by-default-not-icloud)
    - [<u>Disable Adobe Acrobat Updater</u>](#disable-adobe-acrobat-updater)
    - [<u>Transmission Torrent Client</u>](#transmission-torrent-client)
  




***  
  
### <u>Software Update</u>

Checks and install all avaliable software updates.

```bash
softwareupdate -ia
```

***

### <u>iTerm2</u>

iTerm2 brings the terminal into the modern age with features you never knew you always wanted. 

**Download**: [iTerm2](https://iterm2.com/downloads/stable/latest)

**Download**: [iTerm2 Themes](https://github.com/mbadolato/iTerm2-Color-Schemes/zipball/master)

***

### <u>Nerd Fonts</u>

Nerd Fonts is a project that patches developer targeted fonts with a high number of glyphs.

Official Github: [NerdFonts](https://github.com/ryanoasis/nerd-fonts)

Direct Download: [NerdFonts](https://github.com/ryanoasis/nerd-fonts/archive/master.zip)

Use `./install` script to install to your system.

***

### <u>Install Command Line Tools without Xcode</u>

Download the macOS SDK, headers, and build tools. These tools make it easy to install open source software or develop on UNIX.

```bash
xcode-select --install
```

***

### <u>Homebrew</u>

Homebrew installs [the stuff](https://formulae.brew.sh/formula/) you need that Apple didn't. 

**Official Site**: [Homebrew](https://brew.sh/)

**Note:** If you are using Apple Silicon, Homebrew is installed in `/opt/` directory by default instead of `/usr/local/etc` on Intel previously. You will need to change the path `/usr/local/etc` to `/opt/homebrew/etc` in some of the commands for it to work correctly. 

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

**Usage**:

`brew cleanup` `brew doctor` `brew outdated` `brew upgrade` 

**To Uninstall Homebrew**:

```bash
$ ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/uninstall)"
```

***

### <u>ZSH</u>

A powerful shell designed for interactive use. Features of bash, tsh, and tcsh are incorporated into zsh. 

```bash
brew install zsh
```

If necessary, make zsh default shell using this command: `chsh -s $(which zsh)`

***

### <u>Oh My Zsh</u>

Oh My Zsh is a open source framework built on top of zsh for managing it's configuration. This framework will allow us to use themes, plugins, helpers, functions and many other cool things.

**Official Github**: [Oh My Zsh](https://github.com/ohmyzsh/ohmyzsh)

```bash
$ sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

**Install Plugins**: 

```bash
cd ~/.oh-my-zsh/custom/plugins
```
```bash
git clone https://github.com/zsh-users/zsh-syntax-highlighting
```
```bash
git clone https://github.com/zsh-users/zsh-autosuggestions
```

Add `zsh-syntax-highlighting`, `zsh-autosuggestions`, `colored-man-pages` in `~/.zshrc` under plugins. 

**Refresh the Shell Enviornment**:

```bash
source ~/.zshrc	
```

***

### <u>Git</u>

A distributed version control system for tracking changes in souce code during software development.

```bash
brew install git
```

**Git Extras**:

```bash
brew install git-lfs git-flow git-extras
```

**Git Setup**:

```bash
git config --global user.name "your username"
```
```bash
git config --global user.email "your email"
```
```bash
git config --global credential.helper osxkeychain
```
```bash
git config --global color.ui auto
```

***

### <u>SSH Keys</u>

A SSH key is an access credential in the SSH protocol. Its function is similar to that of user names and passwords, but the keys are primarily used for automated processes and for implementing single sign-ons. 

```bash
ssh-keygen -o -a 256 -t ed25519
```
Options:

`-a` rounds

`-o` openssh 

`-t` type

**To copy public key to a particular server**, use: `ssh-copy-id <user@hostname>`

To setup Github, copy and paste SSH key to Github website. 

Use: `pbcopy < ~/.ssh/id_ed25519.pub` to copy to clipboard.

To verify, `ssh -T git@github.com`, you should get the message "Sucessfully Authenticated". 

***

### <u>Powerlevel10k</u>

A theme for Zsh. It emphasizes speed, flexibility, and out-of-the-box expierence. With Powerlevel10k, there is no prompt lag. 

**Official Github**: [Powerlevel10k](https://github.com/romkatv/powerlevel10k)

```bash
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k
```

Set `ZSH_THEME="powerlevel10k/powerlevel10k"` in `~/.zshrc`

```bash
source ~/.zshrc
```

**To configure Powerlevel10k**, use `p10k configure`

***

### <u>Message of the Day</u>

A welcome message shown to a user upon the terminal login. 

```bash
brew install cowsay lolcat fortune
```

`cowsay` generates ASCII pictures of a cow with a message.

`lolcat` is a utility which adds a rainbow coloring to the cat like command. 

`fortune` displays a pseudo-random message from a database of quotations. 

Edit the `~/.zprofile` using the following command:

```bash
nano ~/.zprofile
```
Add: `fortune | cowsay | lolcat`. Save and exit. 

***

### <u>Homebrew Packages</u>

Here are some Homebrew formulae that are useful.

#### **tree**
Display directories as trees
```bash
brew install tree
```
#### **fzf**
Command-Line Fuzzy Finder 
```bash
brew install fzf
```
#### **ack**
Search tool similar to grep, but optimized for programmers
```bash
brew install ack
```
#### **htop**
Improved top (Interactive Process Viewer)
```bash
brew install htop
```
#### **httpd**
Apache HTTP Server
```bash
brew install httpd
```
#### **gcc**
GNU Complier Collection
```bash
brew install gcc
```
#### **mas**
Mac App Store Command Line Interface
```bash
brew install mas
```
#### **neofetch**
Fast, highly customisible system info script
```bash
brew install neofetch
```
#### **nmap**
Port scanning utility for large networks
```bash
brew install nmap
```
#### **openSSH**
OpenBSD SSH connectivity tools
```bash
brew install openssh
```
#### **openSSL**
Cryptography and SSL/TLS toolkit
```bash
brew install openssl
```
#### **p7zip**
7-Zip (High Compression File Archiver)
```bash
brew install p7zip 
```
#### **rsync**
Utility that provides fast incremental file transfer
```bash
brew install rsync 
```
#### **ssh-copy-id**
Add a public key to a remote machine's authorized_keys file
```bash
brew install ssh-copy-id 
```
#### **subnetcalc**
IPv4/IPv6 subnet calculator
```bash
brew install subnetcalc
```
#### **telnet**
User interface to the TELNET protocol
```bash
brew install telnet
```
#### **the silver searcher**
Code search similar to ack
```bash
brew install the_silver_searcher
```
#### **thefuck**
Programmatically correct mistyped console commands
```bash
brew install thefuck
```
#### **TLDR**
Simplified and Community-Driven Man pages
```bash
brew install tldr
```
#### **tmux**
Terminal Multiplexer
```bash
brew install tmux
```
#### **trash**
CLI tool that moves files or folders to the trash
```bash
brew install trash
```
#### **unzip**
Extraction utility for .zip compressed archives
```bash
brew install unzip
```
#### **watch**
Executes a program periodically, showing output fullscreen
```bash
brew install watch
```
#### **wget**
Internet file retriever 
```bash
brew install wget
```
#### **youtube-dl**
Download YouTube videos from the command-line
```bash
brew install youtube-dl
```
#### **vim**
Vi with many additional features
```bash 
brew install vim
```
#### **exa**
Modern replacement for ls command
```bash
brew install exa
```
#### **autojump**
Shell extention to jump to frequently used directories 
```bash
brew install autojump
```
***

### <u>Speedtest CLI by Ookla</u>

Measure internet connection performance metrics like download, upload, latency and packet loss natively without relying on a web browser:

```bash
brew tap teamookla/speedtest
```
```bash
brew update
```
```bash
brew install speedtest --force
```
**Usage**: `$ speedtest`

***

### <u>GPG</u>

GPG is a free software alternative to the closed source commercial PGP. You will also need pinentry-mac. `pinentry-mac` is a tool which prompts with a native dialog box for your GPG key passphrase and also allows you to store the password in your Mac’s keychain. To install GPG and pinentry-mac, use the following command: 

```bash
brew install gpg pinentry-mac
```
To list the GPG keys, use the command:

```bash
gpg --list-keys
```
* Your keyring should be empty at this point. 

To enable pinentry, edit the `$HOME/.gnupg/gpg-agent.conf` file, use the command: 

```bash
echo "pinentry-program /usr/local/bin/pinentry-mac" >> $HOME/.gnupg/gpg-agent.conf
```

To **GENERATE A MASTER KEY**, use the command:

```bash
gpg --expert --full-generate-key
```

* When prompted for what kind of key, pick option: `(8) RSA (set your own capabilities)`.

* When prompted for capabilities, type `s` and hit enter to toggle off the Sign capability.

* Next type `e` and hit enter to toggle off the Encrypt capability.

* Confirm that the current allowed actions only lists Certify, then type `q` and hit enter to finish setting capabilities.

* Now you are prompted for how long the RSA key should be. Type `4096` to set the highest security that GPG currently supports.

* For expiration, I suggest picking `0` so the key doesn’t expire.

* For the Real Name, I suggest picking the same “friendly name” you use for outgoing email.

* Next provide the email address you want to use for receiving encrypted email.

* I will reference this email as `YOUR@EMAIL.com` for the remainder of this install.

* If you’d like to enter a comment for the key, you can do so next. Otherwise hit `enter` to skip it.

* If everything looks good at this point, hit `o` for Okay.

You will now be prompted for your master key passphrase. Please ensure this is a secure password that you have not used anywhere else.

* To set secure preferences on key, use the following command:

```bash
gpg --edit-key YOUR@EMAIL.com
```

* Paste `setpref SHA512 SHA384 SHA256 SHA224 AES256 AES192 AES CAST5 ZLIB BZIP2 ZIP Uncompressed` into it and press `enter`.

* Type `y` to confirm.

* Type `save` to save and exit.

To **ADD A SUBKEY** to be used to encrypt and sign, use the following command:

```bash
gpg --expert --edit-key YOUR@EMAIL.com
```

* At the prompt, type `addkey`.

* Choose option: `(8) RSA (set your own capabilities)` as before.

* Unlike before, the capabilities are already set the way I want (“Sign Encrypt”), so type `q` to finish capability selection.

* Type `4096` as previously done for the keysize.

* Next, we suggest using `0` for no expiration as before.

* Confirm `y` at the next two prompts.

* After entering your passphrase, your subkey is now created.

* Type `save` to quit and exit.


To **EXPORT YOUR PRIVATE KEY**, use the command: 

```bash
gpg --export-secret-keys --armor YOUR@EMAIL.com > YOUR@EMAIL.com.private.gpg-key
```

To **EXPORT YOUR PUBLIC KEY**, use the command: 

```bash
gpg --export --armor YOUR@EMAIL.com > YOUR@EMAIL.com.public.gpg-key
```

To **CREATE A REVOCATION CERTIFICATE**, use the command:
```bash
gpg --output YOUR@EMAIL.com.gpg-revocation-certificate --gen-revoke YOUR@EMAIL.com
```

* Follow the prompts to create the revocation certificate. For reason, I suggest `1 = Key has been compromised` and you can hit enter on the description line (it’s not needed).

* Backup your keys in a safe place. 

I suggest deleting the private key and revocation certificate from your computer afterwards. 

***

### <u>Python</u>

A interpreted, high-level, general-purpose programming language. There are many ways to install Python, but I found this to be best. 

```bash
brew install pyenv
```

```bash
pyenv install -l
```
```bash
pyenv install 3.10.0
```
```bash
pyenv global 3.10.0
```
```bash
pyenv version
```
```bash
echo -e 'if command -v pyenv 1>/dev/null 2>&1; then\n  eval "$(pyenv init -)"\nfi' >> ~/.zshrc
```
```bash
exec $SHELL
```
```bash
which python
```
```bash
python -V
```
```bash
pip -V
```
```bash
pip install --upgrade pip
```

***

### <u>Virtualenv</u>

A tool to create isolated virtual Python environments. 

```bash
pip install virtualenv
```

***

### <u>Pipenv</u>

A packaging tool for Python that solves some common problems associated with the typical workflow using pip, virtualenv, and the good old requirements.txt. 

```bash
brew install pipenv
```

***

### <u>Ruby</u>

A interpreted, high-level, general-purpose programming language. 

```bash
brew install rbenv ruby-build
```
```bash
echo 'if which rbenv > /dev/null; then eval "$(rbenv init -)"; fi' >> ~/.zshrc
```
```bash
source ~/.zshrc
```
```bash
rbenv install -l
```
```bash
rbenv install 3.0.2
```
```bash
rbenv global 3.0.2
```
```bash
exec $SHELL
```
```bash
ruby -v
```

**Usage**:
```bash
# list all available versions installed on the system
rbenv install -l
# install a Ruby version
rbenv install 3.0.1
```
```bash
# set a local application-specific Ruby version in the currrent directory
rbenv local 3.0.1
# set the global version of Ruby to be used in all shells
rbenv global 3.0.1
```

***

### <u>RubyGems and Bundler</u>

Ruby package manager

```bash
which gem
```
```bash
gem install bundler
```

***

### <u>Rails</u>

A web-application framework that includes everything needed to create database-backed web applications. 

```bash
gem install rails -v 6.1.4
```
```bash
rbenv rehash
```
```bash
rails -v
```

***

### <u>MySQL</u>

A open-source relational database management system. 

```bash
brew install mysql
```

```bash
unset TMPDIR
```
```bash
mkdir /usr/local/var
```
```bash
mysql_install_db --verbose --user=`whoami` --basedir="$(brew --prefix mysql)" --datadir=/usr/local/var/mysql --tmpdir=/tmp
```

**Usage**:

Start: `mysql.server start`

Stop: `mysql.server stop`

Help: `mysql.server --help`

Connect CLI: `mysql -uroot`

***

### <u>MySQL Workbench</u>

GUI client for MySQL

```bash
brew install --cask --appdir="/Applications" mysqlworkbench
```

***

### <u>PostgreSQL</u>

A open-source relational database management system emphaszing extensibility and technical standards compliance.

```bash
brew install postgresql
```
```bash
postgres --version
```

**Usage**:

Create Database: `$ initdb /usr/local/var/postgres` 

Start Database: `pg_ctl -D /usr/local/var/postgres start`

Stop Database: `pg_ctl -D /usr/local/var/postgres stop`

Create actual Database: `createdb mydatabasename` , `dropdb mydatabasename`

***

### <u>MongoDB</u>

A popular NoSQL database

```bash
brew tap mongodb/brew
```
```bash
brew install mongodb-community@4.2
```

To start MongoDB: `brew services start mongodb`

***

### <u>Node JS</u>

A open-source, cross-platform,  Javascript runtime enviornment that executes Javascript code outside of a browser. 

```bash
brew install node
```

***

### <u>Yarn</u>

A package manager for your code. It allows your to use and share code with other developers quickly and securely.

```bash
brew install yarn --ignore-dependencies
```

***

### <u>Go Lang</u>

A statically typed, complied programming language designed at Google. Similar to C, but with memory safety, garbarge collection, structural typing, and CSP-style concurrency. 

```bash
brew install go
```

***

### <u>AWS Command Line Interface</u>

A unified tool to manage your AWS service, allowing you to control multiple AWS services from the command line and to automate them through scripts. 

```bash
brew install awscli
```
```bash
aws configure
```

***

### <u>Boto</u>

The official AWS SDK for Python

```bash
pip install boto	
```

***

### <u>Docker</u>

A set of platform as a service products that uses OS-level virtualization to deliver software in packages called containers. 

Download: [Docker for Mac](https://hub.docker.com/editions/community/docker-ce-desktop-mac/)

***

### <u>Java JDK 8</u>

A development enviornment for building applications and components using the Java programming language.

```bash
brew tap homebrew/cask-versions
```
```bash
brew install --cask temurin8
```

***

### <u>Aircrack-ng</u>

A network suite of tools to access WiFi network security. 

```bash
brew install aircrack-ng
```
```bash
sudo ln -s /System/Library/PrivateFrameworks/Apple80211.framework/Versions/Current/Resources/airport /usr/local/bin/airport
```
**Usage**:

* Scan Wifi:  `airport -s`

* Disconnect Wifi:  `airport -z`

* Monitor Mode On:  `sudo airport <interface> sniff <channel>`, e.g. `airport en0 sniff 6`

* Monitor Mode Off:  `ps -ax | grep -a airport.*sniff`

* Brute Hash: `aircrack-ng -1 -a 1 -b <BSSID> <cap_file> -w <wordlist>`

* Kill Processes:  `sudo kill -9 <process id>`

* Cap File Location: `/tmp/airportSniff*.cap`

***

### <u>Apache Server</u>

A open-source cross-platform web server software.

```bash
sudo apachectl stop
```
```bash
sudo launchctl unload -w /System/Library/LaunchDaemons/org.apache.httpd.plist 2>/dev/null
```
```bash
brew install httpd
```
```bash
sudo brew services restart httpd
```
```bash
sudo nano /usr/local/etc/httpd/httpd.conf
```

**Note:** On Apple Silicon, the `httpd.conf` is located in `/opt/homebrew/etc/httpd/httpd.conf`

Find and replace, 

`Listen 8080` to `Listen 80` 

`ServerName www.example.com:8080` to `ServerName localhost`

```bash
$ sudo apachectl -k restart
```

To verify, go to your browser and type "`localhost`" in search bar. You should see `"It Works!"`


***

### <u>PHP</u>

```bash
brew install php@8.0
```
```bash
brew install composer
```

**To test if PHP is working**:

```bash
mkdir test
```
```bash
cd test
```
```bash
composer require atk4/ui
```
```bash
nano test.php
```

Paste the following in PHP file:

```php
<?php
include 'vendor/autoload.php';
$app = new atk4\ui\App('PHP-test');
$app->initLayout('Centered');
$app->add(['Label', 'Your PHP Version:', 'big blue', 'detail'=>phpversion()]);
```

Save and exit.

```bash
php -S 127.0.0.1:8080
```

Now, go on browser and navigate to: `http://127.0.0.1:8080/test.php`

***

### <u>PHP-FPM with Nginx</u>

```bash
brew install nginx
```
```bash
sudo brew services start nginx
```
```bash
brew services start php
```

Edit the server section from `/usr/local/etc/nginx/nginx.conf`

**Note**:  `/opt/homebrew/etc/nginc/nginx.conf` on Apple Silicon. 

```bash
server {
  listen       80;
  server_name  localhost;
  client_max_body_size 20M;
  root   /Users/<YOUR_USER_NAME>/Sites/;
  location / {
    index  index.php index.html index.htm;
  }
  location = /yourapp/ {
    # Simpler version of mod_rewrite catch-all approach
    index index.php;
  }
  location /otherapp/ {
    # Actual URL rewriting
    rewrite ^/[^/]*/(.*) /otherapp/index.php?page=$1;
  }
  location ~ \.php$ {
    fastcgi_pass   127.0.0.1:9000;
    fastcgi_index  index.php;
    # goes on same line:
    fastcgi_param  SCRIPT_FILENAME /Users/rw/Sites/$fastcgi_script_name;
    include        fastcgi_params;
  }
}
```
***

### <u>Sublime Text</u>

A source code editor with a Python application programming interface. Supports many programming languages. 

Download: [Sublime Text 3](https://www.sublimetext.com)

**To block updates**, add the following lines to `/etc/hosts`:

```
127.0.0.1 license.sublimehq.com
127.0.0.1 www.sublimetext.com
```

License Key for Sublime Text 3:  (Working as of 04-20-2021)
Please buy product if you like it!

```
----- BEGIN LICENSE ----
Member J2TeaM 
Single User License 
EA7E-1011316 
D7DA350E 1B8B0760 972F8B60 F3E64036 
B9B4E234 F356F38F 0AD1E3B7 0E9C5FAD 
FA0A2ABE 25F65BD8 D51458E5 3923CE80 
87428428 79079A01 AA69F319 A1AF29A4 
A684C2DC 0B1583D4 19CBD290 217618CD 
5653E0A0 BACE3948 BB2EE45E 422D2C87 
DD9AF44B 99C49590 D2DBDEE1 75860FD2 
8C8BB2AD B2ECE5A4 EFC08AF2 25A9B864
------ END LICENSE ------
```

Settings for Sublime:

```
"auto_complete_commit_on_tab": true, 
"bold_folder_labels": true, 
"enable_line_word_count": true, 
"file_exclude_patterns":
[ 
	".DS_Store" 
], 
"folder_exclude_patterns":
[ 
	"bin", ".bundle", ".git", ".sass-cache", "tmp" 
], 
"hot_exit": false, 
"ignored_packages":
[ 
	"Vintage" 
], 
"open_files_in_new_window": false, 
"remember_open_files": false, 
"rulers":
[ 
	80, 120 
], 
"scroll_past_end": false, 
"scroll_speed": 5.0, 
"show_encoding": true, 
"spell_check": false, 
"tab_size": 2, 
"translate_tabs_to_spaces": true
```

***

### <u>Visual Studio Code</u>

A lightweight code editor with support for many programming languages through extensions.

```bash
brew install --cask visual-studio-code
```

### <u>VirtualBox</u>

Creates and manage virtual machines. A free solution to VMWare.

```bash
brew install --cask --appdir="/Applications" virtualbox
```

***

### <u>Setting up Alias</u>

A list of alias that instucts the shell to replace one string with another string while executing the commands. Like a shortcut. 

Add the following to `~/.zshrc` using the command `nano ~/.zshrc`:

```bash
alias zshconfig="vim ~/.zshrc" 
alias ls="ls -G" 
alias grep="grep -n -G" 
alias ping="ping -c 5" 
alias ps="ps aux" 
alias ll="exa -ll" 
alias mv="mv -vi" 
alias rm="rm -vi" 
alias cp="cp -vi" 
alias untar="tar -xvf" 
alias update="brew update && brew upgrade"
alias ..="cd .."
alias ...="cd ../../../" 
alias ....="cd ../../../../"
alias msfconsole="/opt/metasploit-framework/bin/msfconsole"
alias ghidra="ghidraRUN"
```

***

### <u>Write to NTFS on macOS Catalina</u>

Apple's Mac OS system can always read Windows NTFS formatted drives, but cannot write to them. This method will allow you to write to NTFS formatted drives. 

```bash
brew cask install osxfuse
```
```bash
brew install ntfs-3g
```

Shutdown and reboot the computer into Recovery Mode by holding (⌘-R). Open terminal and enter following command:

```bash
csrutil disable
```
```bash
diskutil list
```

Look for the  `(synthesized)` section with the name `Macintosh HD - Data` , see `Identifier` similar to `disk2s1`.

Replace your `Identifier` in place of `disk2s1` on the following commands.

```bash
diskutil apfs unlockVolume disk2s1 
```
```bash
cd /Volumes/Macintosh HD/sbin 
```
```bash
mv mount_ntfs mount_ntfs.orig 
```
```bash
ln -s /usr/local/sbin/mount_ntfs mount_ntfs 
```
```bash
csrutil enable 
```
```bash
reboot
```

***

### <u>Disable macOS Gatekeeper</u>

Gatekeeper is a security feature of the macOS operation system. It enforces code signing and verifies the downloaded applications before allowing them to run. Disabling this feature will allow your system to run any downloaded software.

```bash
sudo spctl --master-disable
```

***

### <u>Spoof MAC Address</u>

MAC spoofing is a technique for changing a factory-assigned Media Access Control (MAC) address of a network interface on a networked device.

Install SpoofMac:

```bash
brew install spoof-mac
```

To change MAC address automatically from boot:

```bash
sudo nano /Library/LaunchDaemons/local.macspoof.plist
```

**Add these lines**:

```bash
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
    <dict>
        <key>Label</key>
        <string>MacSpoof</string>
        <key>ProgramArguments</key>
        <array>
            <string>/usr/local/bin/spoof-mac.py</string>
            <string>randomize</string>
            <string>en0</string>
        </array>
        <key>RunAtLoad</key>
        <true/>
    </dict>
</plist>
```
**Save and exit. Then reboot system to see changes**.

**Note:** On Apple Silicon, change `<string>/usr/local/bin/spoof-mac.py</string>` to  `<string>/opt/homebrew/bin/spoof-mac.py</string>` in the script above.

To test MAC address after boot, use: `spoof-mac list`

***

If you don't want to install SpoofMac, you can change MAC address manually using the following commands: 

Check existing MAC address:

```bash
ifconfig eno0 | grep ether
```

Generate a random hexadecimal number:

```bash
openssl rand -hex 6 | sed 's/\(..\)/\1:/g; s/.$//'
```

To change MAC address, use:

```bash
sudo ifconfig en0 ether <MAC_ADDRESS>
```
*Note: Replace `<MAC_ADDRESS>` with the one you generated.

***

### <u>Tweaks to macOS</u>

**Reset dock back to default**:
```bash
defaults delete com.apple.dock; killall Dock
```

**Change image type for screenshots**:
```bash
defaults write com.apple.screencapture type -string "png"
```
(Replace `png` with any other i.e. `bmp`, `gif`, `jpg`, `pdf`, `tiff` 


**Avoid creating .DS_Store ﬁles on network or USB volumes**:
```bash
defaults write com.apple.desktopservices DSDontWriteNetworkStores -bool true
```

**Finder: show all ﬁlename extensions**:
```bash
defaults write NSGlobalDomain AppleShowAllExtensions -bool true
```

**Finder: show hidden ﬁles by default**:
```bash
defaults write com.apple.finder AppleShowAllFiles -bool true
```

**Finder: show status bar**:
```bash
defaults write com.apple.finder ShowStatusBar -bool true
```

**Empty Trash securely by default**:
```bash
defaults write com.apple.finder EmptyTrashSecurely -bool true
```

**Full Path in Finder Title Bar**: 
```bash
defaults write com.apple.finder _FXShowPosixPathInTitle -bool YES;
```

**Automatically quit printer app once print jobs has been completed**:
```bash
defaults write com.apple.print.PrintingPrefs "Quit When Finished" -bool true
```

**Disable the “Are you sure you want to open this application?” dialog message**:
```bash
defaults write com.apple.LaunchServices LSQuarantine -bool false
```

**Don't send search queries to Apple in Safari**:
```bash
defaults write com.apple.Safari UniversalSearchEnabled -bool false
```
```bash
defaults write com.apple.Safari SuppressSearchSuggestions -bool true
```

***

### <u>Capture The Flag Tools<u>

A collection of Capture the Flag (CTF) Tools

``` bash
brew install bfg binutils binwalk cifer dex2jar dns2tcp fcrackzip foremost hashpump hydra john knock netpbm pngcheck socat sqlmap tcpflow tcpreplay tcptrace xz ucspi-tcp
```

***

### <u>Ghidra</u>

A software reverse engineering suite of tools developed by NSA.

```bash
brew install --cask ghidra
```
To run, use `ghidraRUN`
	
***
	

### <u>Metasploit Framework</u>

```bash
curl https://raw.githubusercontent.com/rapid7/metasploit-omnibus/master/config/templates/metasploit-framework-wrappers/msfupdate.erb > msfinstall && \
  chmod 755 msfinstall && \
  ./msfinstall
```

To run use: `$ /opt/metasploit-framework/bin/msfconsole`

***

### <u>Recommended Firefox Browser Extensions</u>

A list of Firefox extensions that can help with online privacy. 

```
Bitly 
CanvasBlocker 
CookieAutoDelete 
Decentraleyes 
Google Search Link Fix 
HTTPS Everywhere 
Privacy Badger 
Terms of Service; Didn't Read 
To Google Translate 
uBlock Origin 
User-Agent Switcher 
NoScript
```

***

### <u>Firefox Privacy Focused Configuration</u>

Type `about:config` in the Firefox search bar to edit configurations.

```
media.peerconnection.enabled = false 
media.peerconnection.turn.disable = true 
media.peerconnection.use_document_iceservers = false 
media.peerconnection.video.enabled = false 
media.peerconnection.identity.timeout = 1 
privacy.firstparty.isolate = true 
privacy.trackingprotection.fingerprinting.enabled = true 
privacy.trackingprotection.cryptomining.enabled = true 
privacy.trackingprotection.enabled = true 
browser.send_pings = false 
browser.sessionstore.max_tabs_undo = 0 
browser.urlbar.speculativeConnect.enabled = false 
dom.event.clipboardevents.enabled = false 
media.eme.enabled = false 
media.gmp-widevinecdm.enabled = false 
media.navigator.enabled = false 
network.cookie.cookieBehavior = 1 
network.http.referer.XOriginPolicy = 2 
network.http.referer.XOriginTrimmingPolicy = 2 
webgl.disabled = true 
browser.sessionstore.privacy_level = 2 
network.IDN_show_punycode = true
```

***

### <u>macOS Appearance</u>

Reduce Transparency:
```bash
defaults write com.apple.universalaccess reduceTransparency -bool true
```
Restore Default Transparency:
```bash
defaults write com.apple.universalaccess reduceTransparency -bool false
```

***

### <u>Save to Disk by Default (Not iCloud)</u>

Sets default save target to local disk instead of iCloud

```bash
defaults write -g NSDocumentSaveNewDocumentsToCloud -bool false
```

***

### <u>Disable Adobe Acrobat Updater</u>

```bash
defaults write com.adobe.AdobeUpdater.Admin Disable.Update -bool yes
```

***

### <u>Transmission Torrent Client</u>

Don’t prompt for confirmation before downloading:
```bash
defaults write org.m0k.transmission DownloadAsk -bool false
```
```bash
defaults write org.m0k.transmission MagnetOpenAsk -bool false
```

Don’t prompt for confirmation before removing non-downloading active transfers:
```bash
defaults write org.m0k.transmission CheckRemoveDownloading -bool true
```

Hide the donate message:
```bash
defaults write org.m0k.transmission WarningDonate -bool false
```

Hide the legal disclaimer:
```bash
defaults write org.m0k.transmission WarningLegal -bool false
```

Randomize port on launch:
```bash
defaults write org.m0k.transmission RandomPort -bool true
```

***
<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/80x15.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International License</a>.
