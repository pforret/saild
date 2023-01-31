![bash_unit CI](https://github.com/pforret/saild/workflows/bash_unit%20CI/badge.svg)
![Shellcheck CI](https://github.com/pforret/saild/workflows/Shellcheck%20CI/badge.svg)
![GH Language](https://img.shields.io/github/languages/top/pforret/saild)
![GH stars](https://img.shields.io/github/stars/pforret/saild)
![GH tag](https://img.shields.io/github/v/tag/pforret/saild)
![GH License](https://img.shields.io/github/license/pforret/saild)
[![basher install](https://img.shields.io/badge/basher-install-white?logo=gnu-bash&style=flat)](https://www.basher.it/package/)

# pforret/saild

Start up all you need for a Laravel Sail dev environment in one go
* start Sail containers (Docker)
* open Sail ssh session (Docker)
* open browser on http://[host name]
* upon closing ssh session, shut down Sail

## 🔥 Usage

```
Program : saild  by peter@forret.com
Version : v1.0.1 (2023-01-31 18:32)
Purpose : Start up your Laravel Sail dev environment
Usage   : saild [-h] [-q] [-v] [-f] [-l <log_dir>] [-t <tmp_dir>] [-B <BIN>] [-W <WAIT>] [-U <URL>] <action>
Flags, options and parameters:
    -h|--help        : [flag] show usage [default: off]
    -q|--quiet       : [flag] no output [default: off]
    -v|--verbose     : [flag] also show debug messages [default: off]
    -f|--force       : [flag] do not ask for confirmation (always yes) [default: off]
    -l|--log_dir <?> : [option] folder for log files   [default: /home/pforret/log/saild]
    -t|--tmp_dir <?> : [option] folder for temp files  [default: /tmp/saild]
    -B|--BIN <?>     : [option] sail binary  [default: vendor/bin/sail]
    -W|--WAIT <?>    : [option] seconds to wait for the browser  [default: 5]
    -U|--URL <?>     : [option] URL to open in browser  [default: http://BFLD-PFORRET17]
    <action>         : [choice] action to perform  [options: up,down,init,check,env,update]
```

## ⚡️ Examples

```bash
> saild up
⏳  Docker: start up Sail
[+] Running 7/7
 ⠿ Network project_sail              Created                                                                                                                                                                                                                     0.1s 
 ⠿ Container project-mysql-1         Started                                                                                                                                                                                                                     2.6s
 ⠿ Container project-meilisearch-1   Started                                                                                                                                                                                                                     2.0s 
 ⠿ Container project-mailhog-1       Started                                                                                                                                                                                                                     2.4s 
 ⠿ Container project-redis-1         Started                                                                                                                                                                                                                     2.5s 
 ⠿ Container project-selenium-1      Started                                                                                                                                                                                                                     1.9s 
 ⠿ Container project-laravel.test-1  Started                                                                                                                                                                                                                     3.2s
⏳  Browser: open http://<host name> in 5 secs
⏳  Docker: open bash shell
sail@a163e48d3e8f:/var/www/html$ (...)
exit
⏳  Docker: shut down Sail
[+] Running 7/7
 ⠿ Container project-laravel.test-1  Removed                                                                                                                                                                                                                     0.6s 
 ⠿ Container project-selenium-1      Removed                                                                                                                                                                                                                     4.3s
 ⠿ Container project-redis-1         Removed                                                                                                                                                                                                                     1.2s 
 ⠿ Container project-meilisearch-1   Removed                                                                                                                                                                                                                     1.0s 
 ⠿ Container project-mysql-1         Removed                                                                                                                                                                                                                     2.5s 
 ⠿ Container project-mailhog-1       Removed                                                                                                                                                                                                                     1.4s 
 ⠿ Network project_sail              Removed 
 
 > saild init
 # install Laravel Sail in an existing project
 # https://laravel.com/docs/9.x/sail#installing-sail-into-existing-applications
```

## 🚀 Installation

with [basher](https://github.com/basherpm/basher)

	$ basher install pforret/saild

or with `git`

	$ git clone https://github.com/pforret/saild.git
	$ cd saild

## 📝 Acknowledgements

* script created with [bashew](https://github.com/pforret/bashew)

&copy; 2023 Peter Forret
