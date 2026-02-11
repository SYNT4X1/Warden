```
/$$      /$$  /$$$$$$  /$$$$$$$  /$$$$$$$  /$$$$$$$$ /$$   /$$
| $$  /$ | $$ /$$__  $$| $$__  $$| $$__  $$| $$_____/| $$$ | $$
| $$ /$$$| $$| $$  \ $$| $$  \ $$| $$  \ $$| $$      | $$$$| $$
| $$/$$ $$ $$| $$$$$$$$| $$$$$$$/| $$  | $$| $$$$$   | $$ $$ $$
| $$$$_  $$$$| $$__  $$| $$__  $$| $$  | $$| $$__/   | $$  $$$$
| $$$/ \  $$$| $$  | $$| $$  \ $$| $$  | $$| $$      | $$\  $$$
| $$/   \  $$| $$  | $$| $$  | $$| $$$$$$$/| $$$$$$$$| $$ \  $$
|__/     \__/|__/  |__/|__/  |__/|_______/ |________/|__/  \__/
```  
v1.1.1 | Licensed under MIT
Copyright (c) 2026 Damien Santiago

## Table of Contents

- [About](#-about)
- [Installation](#-installation)
- [Basic Usage](#-basic-usage)
- [Documentation](#-documentation)
- 
- [License](#-license)

## About
Warden is a jail shell utility designed to be used in tandem with best security practices. It enables
administration and logging of users activity within a confined shell environment.


## Installation
clone this repo and run the built-in installer as admin

```
$ ./install
```

## Basic Usage
Warden ships with a couple helpers.

wsh - warden shell </br>
wlog - warden logger </br>
wcfg - warden config </br>

In order to use wlog or wcfg, you will need to add your admin user to the warden-admin group
and then refresh your groups. 
```
$ usermod -aG warden-admin <user>
$ newgrp warden-admin
```
If your user is not in the administration group, the commands will not run. 

-h and --help are flags that dump information on usage.

## Tips
If you want to maximize the utility of this shell, be sure to use it with ssh. If you modify your 
sshd_config and add the following lines

```
Match User *
  ForceCommand /usr/bin/wsh
```

Your ssh config will force dump authenticated users into the warden shell environment. Conversely, this
should also prevent attackers from using the -t ssh flag to obtain a different shell than defined in the /etc/passwd
file 

## Documentation
Coming soon

## License
This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details
