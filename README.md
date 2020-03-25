# MAC OS SETUP

***

### <u>iTerm2</u>

iTerm2 brings the terminal into the modern age with features you never knew you always wanted. 

Download [iTerm2](https://iterm2.com/downloads/stable/latest)

Download [iTerm2 Themes](https://github.com/mbadolato/iTerm2-Color-Schemes/zipball/master)

***

### <u>Command Line Tools for Xcode</u>

Download the macOS SDK, headers, and build tools. These tools make it easy to install open source software or develop on UNIX.

```bash
$ xcode-select --install
```

***

### <u>Homebrew</u>

Homebrew installs [the stuff](https://formulae.brew.sh/formula/) you need that Apple didn't. 

Offical Site: [Homebrew](https://brew.sh/)

```bash
$ /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

Useful commands:

`brew cleanup` `brew doctor` `brew outdated` `brew upgrade` 

***

### <u>Zsh</u>

A powerful shell designed for interactive use. Features of bash, tsh, and tcsh are incorporated into zsh. 

```bash
$ brew install zsh
$ chmod 755 /usr/local/share/zsh
$ chmod 755 /usr/local/share/zsh/site-functions
```

If needed, make zsh default shell using this command `chsh -s $(which zsh)`

***

### <u>Oh My Zsh</u>

A community driven framework for managing your Zsh configuration. It comes bundled with thousands of helpful functions, helpers, plugins, and themes.

Offical Github: [Oh My Zsh](https://github.com/ohmyzsh/ohmyzsh)

```bash
$ sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

```bash
$ cd ~/.oh-my-zsh/custom/plugins
$ git clone https://github.com/zsh-users/zsh-syntax-highlighting
$ git clone https://github.com/zsh-users/zsh-autosuggestions
```

Add `zsh-syntax-highlighting`, `zsh-autosuggestions`, `colored-man-pages` in `~/.zshrc` under plugins. 

```bash
$ source ~/.zshrc	
```

***

### <u>Git</u>

A distributed version control system for tracking changes in souce code during software development.

```bash
$ brew install git
```

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

To copy public key to a particular server, use `ssh-copy-id <user@hostname>`

To setup Github, copy and paste SSH key to Github website. use `pbcopy < ~/.ssh/id_ed25519.pub` to copy to clipboard.

To verify, `ssh -T git@github.com`, you should get message "sucessfully authenticated". 

***

### <u>Powerlevel10k</u>

A theme for Zsh. It emphasizes speed, flexibility, and out-of-the-box expierence. With Powerlevel10k, there is no prompt lag. 

Offical Github: [Powerlevel10k](https://github.com/romkatv/powerlevel10k)

```bash
$ git clone --depth=1 https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k
```

Set `ZSH_THEME="powerlevel10k/powerlevel10k"` in `~/.zshrc`

```bash
$ source ~/.zshrc
```

To configure, use `p10k configure`

***

### <u>Homebrew Packages</u>

```bash
$ brew install tree fzf ack htop httpd gcc mas neofetch nmap openssh openssl p7zip rsync speedtest-cli ssh-copy-id subnetcalc telnet the_silver_searcher thefuck tldr tmux trash unrar unzip watch wget youtube-dl rtv vim exa
```

***

### <u>Python</u>

A interpreted, high-level, general-purpose programming language. There are many ways to install Python, but I found this to be best. 

```bash
$ brew install pyenv
$ pyenv install -l
$ pyenv install 3.8.1
$ pyenv global 3.8.1
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
$ rbenv install 2.7.0
$ rbenv global 2.7.0
$ exec $SHELL
$ ruby -v
```

***

### <u>RubyGems & Bundler</u>

Ruby package manager

```bash
$ which gem
$ gem install bundler
```

***

### <u>Rails</u>

A web-application framework that includes everything needed to create database-backed web applications. 

```bash
$ gem install rails -v 6.0.2.1
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
$ brew install mongo
```

<u>Usage</u>:

Start: `mongod`

Connect: `mongo`

***

### <u>Node.js</u>

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

### <u>Go</u>

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

Download [Docker for Mac](https://hub.docker.com/editions/community/docker-ce-desktop-mac/)

***

### <u>Java JDK 8</u>

A development enviornment for building applications and components using the Java programming language.

```bash
$ brew tap adoptopenjdk/openjdk
$ brew cask install adoptopenjdk8
$ brew install maven
```

***

### <u>Aircrack-ng</u>

A network suite of tools to access WiFi network security. 

```bash
$ brew install aircrack-ng
$ sudo ln -s /System/Library/PrivateFrameworks/Apple80211.framework/Versions/Current/Resources/airport /usr/local/bin/airport
```

Scan Wifi:  `airport -s`

Disconnect Wifi:  `airport -z`

Monitor Mode On:  `sudo airport <interface> sniff <channel>`, e.g. `airport en0 sniff 6`

Monitor Mode Off:  `ps -ax | grep -a airport.*sniff`

Brute Hash: `aircrack-ng -1 -a 1 -b <BSSID> <cap_file> -w <wordlist>`

Kill Processes:  `sudo kill -9 <process id>`

Cap File Location: `/tmp/airportSniff*.cap`

***

### <u>Apache</u>

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
$ brew install php@7.4
$ brew isntall composer
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

Download [Sublime Text 3](https://www.sublimetext.com)

Add the following lines to `/etc/hosts`:

```
127.0.0.1 license.sublimehq.com
127.0.0.1 www.sublimetext.com
```

License Key for Sublime Text 3:  (Working as of 03-05-2020)
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

Creates and managew virtual machines. A free solution to VMWare.

```bash
brew cask install --appdir="/Applications" virtualbox
```

***

### <u>Alias</u>

A list of alias that instucts the shell to replace one string with another string while executing the commands. Like a shortcut. 

Add to `~/.zshrc`.

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

Reboot into Recovery Mode (⌘-R). Open terminal and enter following command

```bash
$ csrutil disable
$ diskutil list
```

Look for the  `(synthesized)` section with the name `Macintosh HD - Data` , see `Identifier` similar to `disk2s1`.

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

Alternative: If you don't want to install SpoofMac

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

Reveal IP address, hostname, OS version, etc. when clicking the clock in the login window:

```bash
$ defaults write /Library/Preferences/com.apple.loginwindow AdminHostInfo HostName
```

Avoid creating .DS_Store ﬁles on network volumes:

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

### <u>Firefox Configuration</u>

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
