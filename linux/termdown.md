## Beautiful countdown to use on lives 

On making lives about programming just when I need get out from PC I needed a timer. 
So a decided to make one using termdown.

```sh
#!/bin/bash
# Dependency: termdown
# pip3 install termdown

# I recommend to install termdown inside a python3 venv that you have in your $PATH instead of on your system python
if [[ $@ == "" ]]
then
    termdown -f roman -T "Be  Right      Back" 5 && termdown -f roman -T 'Luiz Correia is LATE !'
elif ! [ $1 -eq $1 ] 2>/dev/null
then
    echo $1 is not an INTEGER to use as minutes
else
    termdown -f roman -T "Be  Right      Back" $(expr $1 \* 60) && termdown -f roman -T 'Luiz Correia is LATE !'
fi
```