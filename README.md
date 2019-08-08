# Theme
A simple termux theme manager

## Usage
- `theme [-l]` to list the themes
- `theme <name>` to apply a theme
- `theme -c <name>` to apply the colors of a theme
- `theme -f <name>` to apply the font of a theme
- `theme -o <name>` to export the current theme
- `theme -e` to edit the current theme in `vi` or the default editor, if found
- `theme -s <key> <value>` sets the corresponding property in the current theme


- The `-c` and `-f` flags are mutually exclusive.
- The `-s`, `-e` and `-o` can be combined and will be executed in this order.
- `-s` can be used any number of times, and will be executed in the order they appear in the command line.


The themes are stored in the `~/themes` directory.

## Installing
To install, simply download the `theme` file from this repo, and put it somewhere in your path, with the execute permission. Make sure you have lua >= 5.2 installed and available.

```sh
# install lua if it is not already present
which lua > /dev/null || apt install lua

# create bin directory if absent
mkdir -p ~/bin

# download and make executable theme script
curl -sL "https://raw.githubusercontent.com/natnat-mc/theme/master/theme" > ~/bin/theme
chmod +x ~/bin/theme

# add bin directory to path if absent
bash -l -c "which theme" > /dev/null || echo "[ -d $HOME/bin ] && export PATH=$HOME/bin:"'$PATH' >> ~/.bashrc
```
