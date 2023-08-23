

```
rm ~/.bashrc &> /dev/null
cat <<EOF >> ~/.bashrc

alias l="ls -a"
alias la="ls -a"
alias c="clear"
alias e="exit 0"
alias 00="kill \"\$PPID\""

prompt_color='\[\033[5;31m\]'
info_color='\[\033[1;34m\]'
prompt_symbol=💀

PS1=\$prompt_color'┌──\${debian_chroot:+(\$debian_chroot)──}\${VIRTUAL_ENV:+(\\\[\033[0;1m\\\]\$(basename \$VIRTUAL_ENV)'\$prompt_color')}('\$info_color'•💀•TERMUX•💀•'\$prompt_color')-[\[\033[0;1m\]\w'\$prompt_color']\\n'\$prompt_color'└─'\$info_color'\$\\[\033[0m\\] '

unset prompt_color
unset info_color
unset prompt_symbol

if [ -f ~/.bash_history ]; then
    file_mtime=\$(stat -c %Y ~/.bash_history)
    current_time=\$(date +%s)
    time_threshold=270
    time_diff=\$((current_time - file_mtime))

    if [ \$time_diff -ge \$time_threshold ]; then
        rm ~/.bash_history &> /dev/null
        touch ~/.bash_history
    fi
fi
EOF
printf "\033[5;32m[!]Login Ulang\n"
sleep 1
for countdown in 3 2 1; do
    echo -ne "\r\033[34mHitung Mundur $countdown"
    sleep 0.4
done 
kill $PPID
```
