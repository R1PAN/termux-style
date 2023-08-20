#```
alias l= "ls -a"
# Konfigurasi warna untuk prompt
prompt_color='\[\033[01;32m\]'
info_color='\[\033[1;34m\]'
prompt_symbol=💀
# Konfigurasi prompt dengan warna
PS1=$prompt_color'┌──${debian_chroot:+($debian_chroot)──}${VIRTUAL_ENV:+(\[\033[0;1m\]$(basename $VIRTUAL_ENV)'$prompt_color')}('$info_color'Pan'$prompt_symbol'\h'$prompt_color')-[\[\033[0;1m\]\w'$prompt_color']\n'$prompt_color'└─'$info_color'\$\[\033[0m\] '

unset prompt_color
unset info_color
unset prompt_symbol
```
