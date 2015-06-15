connect-to
===

# What is it?
Simple command-line connection manager.

# Requirements
Any sh-compatible command language interpreter for running script, grep and Coreutils. For now autocompletion works with zsh only.

# Installing
Download, review, modify vars in script. 
If you want autocomletion, then place file _connect-to somewhere in your $fpath. If you don’t want (or don’t have the permission) to add files into a directory in $fpath, you can create a directory in your home directory (for example, .config/zsh/completions/) and prepend that directory to the list in $fpath by adding these commands to your $HOME/.zshrc.

fpath=(~/.config/zsh/completions $fpath)

autoload -Uz compinit
compinit

Place .myhosts in your $HOMEDIR (it's default) and add some your favorite host(-s) in it like in exapmple:
localhost;ssh;alksf@127.0.0.1;My favorite host
google;browser;https://google.com;Google Search
router;telnet;192.168.1.1;My Homenet router

.myhosts is semicolon delimited csv file. Format of .myhosts file:
1. Identifier of host (hostname e.g.)
2. Connection method. ssh, as usual, but it cat be any you like: telnet, browser.
3. username@hostname for ssh, hostname for telnet, URL for browser, etc.
4. Description. It's optional, you can write here any description or comment here.

Then execute the script

# Usage
$connect-to [OPTION]/[HOST]
-c - Connect to host
-l - List hosts
-m - Mount host by sshfs
-s - Search host[-s]
