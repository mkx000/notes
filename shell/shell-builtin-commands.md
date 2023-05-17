# Bash builtin commands
1. help command: 
	
``` bash
# display all bash builtin commands
help
# help usage
help help
# show the type of command
type command...
```

# Zsh builtin commands
1. help built-in commands
```bash
# run-help is the same as "help" of bash in zsh
# config run-help to help
unalias run-help 2>/dev/null # don't show error if already done
autoload -Uz run-help # load the function
HELPDIR=/usr/share/zsh/help  
alias help=run-help

# optinal autoload modules
autoload run−help−git
autoload run−help−ip
autoload run−help−openssl
autoload run−help−p4
autoload run−help−sudo
autoload run−help−svk
autoload run−help−svn
```
