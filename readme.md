## Get Started
***

   * [Check for Software Updates](#check-for-updates)  
   * [Download and Install iTerm2](#iterm2)
   * [Nerd Fonts](#nerd-fonts)
   * [Install Command Line Tools](#install-command-line-tools-without-xcode)
   * [Install Homebrew](#homebrew)
   * [Install ZSH](#zsh)
   * [Install Oh My Zsh](#oh-my-zsh)
   * [Install Git](#git)
   * [Generate SSH Keys](#generate-ssh-keys)
   * [Install Powerlevel10K](#powerlevel10k)
   * [Setup Message of the Day(MOTD)](#message-of-the-day)
   * [Install Homebrew Packages](#homebrew-packages)
   * [Install Speedtest CLI by Ookla](#speedtest-cli-by-ookla)
   * [Setup GPG Keys](#gpg)
   * [Add Useful Aliases](#alias)
   * [Install Python](#python)
   * [Install Virtualenv](#virtualenv)
   * [Install Pipenv](#pipenv)
   * [Install Ruby](#ruby)
   * [Update Rubygems and Bundler](#rubygems-and-bundler)
   * [Install Rails](#rails)
   * [Install MySQL](#mysql)
   * [Install MySQL Workbench](#mysql-workbench)
   * [Install PostgreSQL](#postgresql)
   * [Install MongoDB](#mongodb)
   * [Install Node](#node-js)
   * [Install Yarn](#yarn)
   * [Install Go Lang](#go)
   * [Install AWS CLI](#aws-command-line-interface)
   * [Install Boto](#boto)
   * [Install Docker](#docker)
   * [Install Java JDK 11](#java-jdk-11)
   * [Install Aircrack-ng](#aircrack-ng)
   * [Setup Apache Server](#apache)
   * [Install PHP](#php)
   * [Setting up PHP-FPM with Nginx](#setting-up-php-fpm-with-nginx)
   * [Install Aircrack-ng](#aircrack-ng)
   * [Install CTF Tools](#ctf-tools)
   * [Install Metasploit](#metasploit-framework)
   * [Install VirtualBox](#virtualbox)
   * [Install Sublime Text 3](#sublime-text-3)
   * [Install Visual Studio Code](#visual-studio-code)
   * [Write to NTFS on MacOS Catalina](#write-to-ntfs-on-macos-catalina)
   * [Disable Gatekeeper](#disable-gatekeeper)
   * [Spoofing MAC Address](#spoof-mac-address)
   * [Tweaks](#tweaks)
   * [Tweak Appearance](#macos-appearance)
   * [Save files to disk by default](#save-to-disk-by-default)
   * [Firefox Browser Extensions](#firefox-browser-extensions)
   * [Firefox Privacy Configurations](#firefox-privacy-focused-configuration)
   * [Disable Adobe Acrobat Updater](#disable-adobe-acrobat-updater)
   * [Tweaks for Transmission App](#transmission-app)
   
***  
  
  
  
  

### Check for updates

Checks and install all avaliable software updates.

```bash
$ softwareupdate -ia
```

***

### <u>iTerm2</u>

iTerm2 brings the terminal into the modern age with features you never knew you always wanted. 

Download: [iTerm2](https://iterm2.com/downloads/stable/latest)

Download: [iTerm2 Themes](https://github.com/mbadolato/iTerm2-Color-Schemes/zipball/master)

***

### Nerd Fonts

Nerd Fonts is a project that patches developer targeted fonts with a high number of glyphs (icons).

Official Github: [NerdFonts](https://github.com/ryanoasis/nerd-fonts)

Direct Download: [NerdFonts](https://github.com/ryanoasis/nerd-fonts/archive/master.zip)

Unzip and use `./install` script to install to your system.

***

### <u>Install Command Line Tools without Xcode</u>

Download the macOS SDK, headers, and build tools. These tools make it easy to install open source software or develop on UNIX.

```bash
$ xcode-select --install
```

***

### <u>Homebrew</u>

Homebrew installs [the stuff](https://formulae.brew.sh/formula/) you need that Apple didn't. 

Official Site: [Homebrew](https://brew.sh/)

```bash
$ /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

Useful commands:

`brew cleanup` `brew doctor` `brew outdated` `brew upgrade` 

To uninstall Homebrew:

```bash
$ ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/uninstall)"
```

***

### <u>ZSH</u>

A powerful shell designed for interactive use. Features of bash, tsh, and tcsh are incorporated into zsh. 

```bash
$ brew install zsh
```

If necessary, make zsh default shell using this command: `chsh -s $(which zsh)`

***

### <u>Oh My Zsh</u>

Oh My Zsh is a open source framework built on top of zsh for managing it's configuration. This framework will allow us to use themes, plugins, helpers, functions and many other cool things.

Official Github: [Oh My Zsh](https://github.com/ohmyzsh/ohmyzsh)

```bash
$ sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```
Change file permissions for the following folders:

```bash
$ chmod 755 /usr/local/share/zsh
$ chmod 755 /usr/local/share/zsh/site-functions
```
Install plugins: 

```bash
$ cd ~/.oh-my-zsh/custom/plugins
$ git clone https://github.com/zsh-users/zsh-syntax-highlighting
$ git clone https://github.com/zsh-users/zsh-autosuggestions
```

Add `zsh-syntax-highlighting`, `zsh-autosuggestions`, `colored-man-pages` in `~/.zshrc` under plugins. 

Refresh the shell enviornment:

```bash
$ source ~/.zshrc	
```

***

### <u>Git</u>

A distributed version control system for tracking changes in souce code during software development.

```bash
$ brew install git
```

Git extras:

```bash
$ brew install git-lfs git-flow git-extras
```

Git setup:

```bash
$ git config --global user.name "your username"
$ git config --global user.email "your email"
$ git config --global credential.helper osxkeychain
$ git config --global color.ui auto
```

***

### <u>Generate SSH Keys</u>

A SSH key is an access credential in the SSH protocol. Its function is similar to that of user names and passwords, but the keys are primarily used for automated processes and for implementing single sign-ons. 

```bash
$ ssh-keygen -o -a 256 -t ed25519
```
Options:

`-a` rounds
`-o` openssh 
`-t` type

To copy public key to a particular server, use: `ssh-copy-id <user@hostname>`

To setup Github, copy and paste SSH key to Github website. use: `pbcopy < ~/.ssh/id_ed25519.pub` to copy to clipboard.

To verify, `ssh -T git@github.com`, you should get message "sucessfully authenticated". 

***

### <u>Powerlevel10k</u>

A theme for Zsh. It emphasizes speed, flexibility, and out-of-the-box expierence. With Powerlevel10k, there is no prompt lag. 

Official Github: [Powerlevel10k](https://github.com/romkatv/powerlevel10k)

```bash
$ git clone --depth=1 https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k
```

Set `ZSH_THEME="powerlevel10k/powerlevel10k"` in `~/.zshrc`

```bash
$ source ~/.zshrc
```

To configure, use `p10k configure`

***

### Message of the Day

A welcome message shown to a user upon the terminal login. 

```bash
$ brew install cowsay lolcat fortune
```

`cowsay` generates ASCII pictures of a cow with a message.
`lolcat` is a utility which adds a rainbow coloring to the cat like command. 
`fortune` displays a pseudo-random message from a database of quotations. 

Edit the `~/.zprofile` using the following command:

```bash
$ vim ~/.zprofile
```
Add: `fortune | cowsay | lolcat`. Save and exit. 

***

### <u>Homebrew Packages</u>

```bash
$ brew install tree
```
```bash
$ brew install fzf
```
```bash
$ brew install ack
```
```bash
$ brew install htop
```
```bash
$ brew install httpd
```
```bash
$ brew install gcc
```
```bash
$ brew install mas
```
```bash
$ brew install neofetch
```
```bash
$ brew install nmap
```
```bash
$ brew install openssh
```
```bash
$ brew install openssl
```
```bash
$ brew install p7zip 
```
```bash
$ brew install rsync 
```
```bash
$ brew install ssh-copy-id 
```
```bash
$ brew install subnetcalc
```
```bash
$ brew install telnet
```
```bash
$ brew install the_silver_searcher
```
```bash
$ brew install thefuck
```
```bash
$ brew install tldr
```
```bash
$ brew install tmux
```
```bash
$ brew install trash
```
```bash
$ brew install unzip
```
```bash
$ brew install watch
```
```bash
$ brew install wget
```
```bash
$ brew install youtube-dl
```
```bash 
$ brew install vim
```
```bash
$ brew install exa
```
```bash
$ brew install autojump
```

***

### <u>Speedtest CLI by Ookla</u>

Measure internet connection performance metrics like download, upload, latency and packet loss natively without relying on a web browser:

```bash
$ brew tap teamookla/speedtest
$ brew update
$ brew install speedtest --force
```
Usage: `$ speedtest`

***

### GPG

GPG is a free software alternative to the closed source commercial PGP. You will also need pinentry-mac. `pinentry-mac` is a tool which prompts with a native dialog box for your GPG key passphrase and also allows you to store the password in your Mac’s keychain. To install GPG and pinentry-mac, use the following command: 

```bash
$ brew install gpg pinentry-mac
```
To list the GPG keys, use the command:

```bash
$ gpg --list-keys
```
* Your keyring should be empty at this point. 

To enable pinentry, edit the `$HOME/.gnupg/gpg-agent.conf` file, use the command: 

```bash
$ echo "pinentry-program /usr/local/bin/pinentry-mac" >> $HOME/.gnupg/gpg-agent.conf
```

To **GENERATE A MASTER KEY**, use the command:

```bash
$ gpg --expert --full-generate-key
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
$ gpg --edit-key YOUR@EMAIL.com
```

* Paste `setpref SHA512 SHA384 SHA256 SHA224 AES256 AES192 AES CAST5 ZLIB BZIP2 ZIP Uncompressed` into it and press `enter`.

* Type `y` to confirm.

* Type `save` to save and exit.

To **ADD A SUBKEY** to be used to encrypt and sign, use the following command:

```bash
$ gpg --expert --edit-key YOUR@EMAIL.com
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
$ gpg --export-secret-keys --armor YOUR@EMAIL.com > YOUR@EMAIL.com.private.gpg-key
```

To **EXPORT YOUR PUBLIC KEY**, use the command: 

```bash
$ gpg --export --armor YOUR@EMAIL.com > YOUR@EMAIL.com.public.gpg-key
```

To **CREATE A REVOCATION CERTIFICATE**, use the command:
```bash
$ gpg --output YOUR@EMAIL.com.gpg-revocation-certificate --gen-revoke YOUR@EMAIL.com
```

* Follow the prompts to create the revocation certificate. For reason, I suggest `1 = Key has been compromised` and you can hit enter on the description line (it’s not needed).

* Backup your keys in a safe place. 

I suggest deleting the private key and revocation certificate from your computer afterwards. 

***

### <u>Python</u>

A interpreted, high-level, general-purpose programming language. There are many ways to install Python, but I found this to be best. 

```bash
$ brew install pyenv
$ pyenv install -l
$ pyenv install 3.9.4
$ pyenv global 3.9.4
$ pyenv version
$ echo -e 'if command -v pyenv 1>/dev/null 2>&1; then\n  eval "$(pyenv init -)"\nfi' >> ~/.zshrc
$ exec $SHELL
$ which python
$ python -V
$ pip -V
$ pip install --upgrade pip
```

***

### <u>Virtualenv</u>

A tool to create isolated virtual Python environments. 

```bash
$ pip install virtualenv
```

***

### <u>Pipenv</u>

A packaging tool for Python that solves some common problems associated with the typical workflow using pip, virtualenv, and the good old requirements.txt. 

```bash
$ brew install pipenv
```

***

### <u>Ruby</u>

A interpreted, high-level, general-purpose programming language. 

```bash
$ brew install rbenv ruby-build
$ echo 'if which rbenv > /dev/null; then eval "$(rbenv init -)"; fi' >> ~/.zshrc
$ source ~/.zshrc
$ rbenv install -l
$ rbenv install 3.0.1
$ rbenv global 3.0.1
$ exec $SHELL
$ ruby -v
```

***

### <u>RubyGems and Bundler</u>

Ruby package manager

```bash
$ which gem
$ gem install bundler
```

***

### <u>Rails</u>

A web-application framework that includes everything needed to create database-backed web applications. 

```bash
$ gem install rails -v 6.1.3.1
$ rbenv rehash
$ rails -v
```

***

### <u>MySQL</u>

A open-source relational database management system. 

```bash
$ brew install mysql
```

```bash
$ unset TMPDIR
$ mkdir /usr/local/var
$ mysql_install_db --verbose --user=`whoami` --basedir="$(brew --prefix mysql)" --datadir=/usr/local/var/mysql --tmpdir=/tmp
```

<u>Usage</u>:

Start: `mysql.server start`

Stop: `mysql.server stop`

Help: `mysql.server --help`

Connect CLI: `mysql -uroot`

***

### <u>MySQL Workbench</u>

GUI client for MySQL

```bash
$ brew cask install --appdir="/Applications" mysqlworkbench
```

***

### <u>PostgreSQL</u>

A open-source relational database management system emphaszing extensibility and technical standards compliance.

```bash
$ brew install postgresql
$ postgres --version
```

<u>Usage</u>:

Create Database: `$ initdb /usr/local/var/postgres` 

Start Database: `pg_ctl -D /usr/local/var/postgres start`

Stop Database: `pg_ctl -D /usr/local/var/postgres stop`

Create actual Database: `createdb mydatabasename` , `dropdb mydatabasename`

***

### <u>MongoDB</u>

A popular NoSQL database

```bash
$ brew tap mongodb/brew
$ brew install mongodb-community@4.2
```

To start MongoDB: `brew services start mongodb`

***

### <u>Node JS</u>

A open-source, cross-platform,  Javascript runtime enviornment that executes Javascript code outside of a browser. 

```bash
$ brew install node
```

***

### <u>Yarn</u>

A package manager for your code. It allows your to use and share code with other developers quickly and securely.

```
$ brew install yarn --ignore-dependencies
```

***

### <u>Go Lang</u>

A statically typed, complied programming language designed at Google. Similar to C, but with memory safety, garbarge collection, structural typing, and CSP-style concurrency. 

```bash
$ brew install go
```

***

### <u>AWS Command Line Interface</u>

A unified tool to manage your AWS service, allowing you to control multiple AWS services from the command line and to automate them through scripts. 

```bash
$ brew install awscli
$ aws configure
```

***

### <u>Boto</u>

The official AWS SDK for Python

```bash
$ pip install boto	
```

***

### <u>Docker</u>

A set of platform as a service products that uses OS-level virtualization to deliver software in packages called containers. 

Download: [Docker for Mac](https://hub.docker.com/editions/community/docker-ce-desktop-mac/)

***

### <u>Java JDK 11</u>

A development enviornment for building applications and components using the Java programming language.

```bash
$ brew tap adoptopenjdk/openjdk
$ brew install adoptopenjdk11
$ brew install maven
```

***

### <u>Aircrack-ng</u>

A network suite of tools to access WiFi network security. 

```bash
$ brew install aircrack-ng
$ sudo ln -s /System/Library/PrivateFrameworks/Apple80211.framework/Versions/Current/Resources/airport /usr/local/bin/airport
```
Usage:

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
$ sudo apachectl stop
$ sudo launchctl unload -w /System/Library/LaunchDaemons/org.apache.httpd.plist 2>/dev/null
$ brew install httpd
$ sudo brew services restart httpd
$ sudo nano /usr/local/etc/httpd/httpd.conf
```

Find and replace, `Listen 8080` to `Listen 80` , and `ServerName www.example.com:8080` to `ServerName localhost`

```bash
$ sudo apachectl -k restart
```

To verify, go to browser and type "`localhost`" in search bar. You should see `"It Works!"`

***

### <u>PHP</u>

```bash
$ brew install php@8.0
$ brew install composer
```

Test:

```bash
$ mkdir test
$ cd test
$ composer require atk4/ui
$ nano test.php
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
$ php -S 127.0.0.1:8080
```

Now, go on browser and navigate to: `http://127.0.0.1:8080/test.php`

***

### <u>Setting up php-fpm with Nginx</u>

```bash
$ brew install nginx
$ sudo brew services start nginx
$ brew services start php
```

Edit the server section from `/usr/local/etc/nginx/nginx.conf`

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

### <u>Sublime Text 3</u>

A source code editor with a Python application programming interface. Supports many programming languages. 

Download: [Sublime Text 3](https://www.sublimetext.com)

To block updates, add the following lines to `/etc/hosts`:

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
$ brew cask install visual-studio-code
```

### <u>VirtualBox</u>

Creates and manage virtual machines. A free solution to VMWare.

```bash
brew cask install --appdir="/Applications" virtualbox
```

***

### <u>Alias</u>

A list of alias that instucts the shell to replace one string with another string while executing the commands. Like a shortcut. 

Add the following to `~/.zshrc` using the command `vim ~/.zshrc`:

```
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
```

***

### <u>Write to NTFS on macOS Catalina</u>

Apple's Mac OS system can always read Windows NTFS formatted drives, but cannot write to them. This method will allow you to write to NTFS formatted drives. 

```bash
$ brew cask install osxfuse
$ brew install ntfs-3g
```

Reboot into Recovery Mode (⌘-R). Open terminal and enter following command:

```bash
$ csrutil disable
$ diskutil list
```

Look for the  `(synthesized)` section with the name `Macintosh HD - Data` , see `Identifier` similar to `disk2s1`.

Replace your `Identifier` in place of `disk2s1` on the following commands.

```bash
$ diskutil apfs unlockVolume disk2s1 
$ cd /Volumes/Macintosh HD/sbin 
$ mv mount_ntfs mount_ntfs.orig 
$ ln -s /usr/local/sbin/mount_ntfs mount_ntfs 
$ csrutil enable 
$ reboot
```

***

### <u>Disable Gatekeeper</u>

Gatekeeper is a security feature of the macOS operation system. It enforces code signing and verifies the downloaded applications before allowing them to run. Disabling this feature will allow your system to run any downloaded software.

```bash
$ sudo spctl --master-disable
```

***

### <u>Spoof MAC Address</u>

MAC spoofing is a technique for changing a factory-assigned Media Access Control (MAC) address of a network interface on a networked device.

Install SpoofMac:

```bash
$ brew install spoof-mac
$ sudo spoof-mac randomize en0
```
Change MAC address automatically from boot:

```bash
$ sudo nano /Library/LaunchDaemons/local.macspoof.plist
```

Add these lines:

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
Save and exit. Then Reboot.

To test MAC address after boot, use: `spoof-mac list`

***

If you don't want to install SpoofMac, you can change MAC address manually using the following commands: 

Check existing MAC address:

```bash
$ ifconfig eno0 | grep ether
```

Generate a random hexadecimal number:

```bash
$ openssl rand -hex 6 | sed 's/\(..\)/\1:/g; s/.$//'
```

To change MAC address, use:

```bash
$ sudo ifconfig en0 ether <MAC_ADDRESS>
```
*Note: Replace `<MAC_ADDRESS>` with the one you generated.

***

### <u>Tweaks</u>

Reset dock back to default:
```bash
$ defaults delete com.apple.dock; killall Dock
```

Change image type for screenshots:
```bash
$ defaults write com.apple.screencapture type -string "png"
```
(Replace `png` with any other i.e. `bmp`, `gif`, `jpg`, `pdf`, `tiff` 


Avoid creating .DS_Store ﬁles on network or USB volumes:
```bash
$ defaults write com.apple.desktopservices DSDontWriteNetworkStores -bool true
```

Finder: show all ﬁlename extensions:
```bash
$ defaults write NSGlobalDomain AppleShowAllExtensions -bool true
```

Finder: show hidden ﬁles by default:
```bash
$ defaults write com.apple.finder AppleShowAllFiles -bool true
```

Finder: show status bar:
```bash
$ defaults write com.apple.finder ShowStatusBar -bool true
```

Empty Trash securely by default:
```bash
$ defaults write com.apple.finder EmptyTrashSecurely -bool true
```

Full Path in Finder Title Bar: 
```bash
$ defaults write com.apple.finder _FXShowPosixPathInTitle -bool YES;
```

Automatically quit printer app once print jobs has been completed:
```bash
$ defaults write com.apple.print.PrintingPrefs "Quit When Finished" -bool true
```

Disable the “Are you sure you want to open this application?” dialog message:
```bash
$ defaults write com.apple.LaunchServices LSQuarantine -bool false
```

Reveal IP address, hostname, OS version, etc. when clicking the clock in the login window
```bash
$ sudo defaults write /Library/Preferences/com.apple.loginwindow AdminHostInfo HostName
```

Don't send search queries to Apple in Safari:
```bash
$ defaults write com.apple.Safari UniversalSearchEnabled -bool false
$ defaults write com.apple.Safari SuppressSearchSuggestions -bool true
```

***

### CTF Tools

A collection of Capture the Flag (CTF) Tools

``` bash
$ brew install bfg binutils binwalk cifer dex2jar dns2tcp fcrackzip foremost hashpump hydra john knock netpbm pngcheck socat sqlmap tcpflow tcpreplay tcptrace xz ucspi-tcp
```

***

### Metasploit Framework 

```bash
$ curl https://raw.githubusercontent.com/rapid7/metasploit-omnibus/master/config/templates/metasploit-framework-wrappers/msfupdate.erb > msfinstall && \
  chmod 755 msfinstall && \
  ./msfinstall
```

To run use: `$ /opt/metasploit-framework/bin/msfconsole`

***

### <u>Firefox Browser Extensions</u>

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

### macOS Appearance 

Reduce Transparency:
```bash
$ defaults write com.apple.universalaccess reduceTransparency -bool true
```
Restore Default Transparency:
```bash
$ defaults write com.apple.universalaccess reduceTransparency -bool false
```

***

### Save to Disk by Default (Not iCloud)

Sets default save target to local disk instead of iCloud

```bash
$ defaults write -g NSDocumentSaveNewDocumentsToCloud -bool false
```

***

### Disable Adobe Acrobat Updater

```bash
$ defaults write com.adobe.AdobeUpdater.Admin Disable.Update -bool yes
```

***

### Transmission App

Don’t prompt for confirmation before downloading:
```bash
$ defaults write org.m0k.transmission DownloadAsk -bool false
$ defaults write org.m0k.transmission MagnetOpenAsk -bool false
```

Don’t prompt for confirmation before removing non-downloading active transfers:
```bash
$ defaults write org.m0k.transmission CheckRemoveDownloading -bool true
```

Hide the donate message:
```bash
$ defaults write org.m0k.transmission WarningDonate -bool false
```

Hide the legal disclaimer:
```bash
$ defaults write org.m0k.transmission WarningLegal -bool false
```

Randomize port on launch:
```bash
$ defaults write org.m0k.transmission RandomPort -bool true
```

***
<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/80x15.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International License</a>.
