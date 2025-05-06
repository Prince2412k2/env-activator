# Activator

its a pain to write source ./env(venv)/bin/activate everytime i open a project

> at ~/.local/scripts/act

```bash

#!/bin/bash
get_env() {
  if [ -d ".env" ]; then
    get_activate ".env"
  elif [ -d ".venv" ]; then
    get_activate ".venv"
  else
    echo "Python env not found in $(pwd)"
  fi
}

get_activate() {
  if [ -f "$1/bin/activate" ]; then
    source "$1/bin/activate"
  else
    echo "Activate script not found in $1"
  fi
}

get_env

```

> at ~/.bashrc

```bash

## Add scripts to path
PATH="$PATH":"$HOME/.local/scripts/"

## add Alias
alias act="source act"
##
```

> Make sure to make the script(act) in ~/.local/scripts is excecutable

```bash
chmod +x ~/.local/scripts/act
```
