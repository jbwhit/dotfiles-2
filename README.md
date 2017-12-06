# Setting up your system

Inspired by: holman does dotfiles

## topical

Everything's built around topic areas. If you're adding a new area to your
forked dotfiles — say, "Java" — you can simply add a `java` directory and put
files in there. Anything with an extension of `.zsh` will get automatically
included into your shell. Anything with an extension of `.symlink` will get
symlinked without extension into `$HOME` when you run `script/bootstrap`.

## what's inside

A lot of stuff. Seriously, a lot of stuff. Check them out in the file browser
above and see what components may mesh up with you.
[Fork it](https://github.com/holman/dotfiles/fork), remove what you don't
use, and build on what you do use.

## components

There's a few special files in the hierarchy.

- **bin/**: Anything in `bin/` will get added to your `$PATH` and be made
  available everywhere.
- **Brewfile**: This is a list of applications for [Homebrew Cask](https://caskroom.github.io) to install: things like Chrome and 1Password and Adium and stuff. Might want to edit this file before running any initial setup.
- **topic/\*.zsh**: Any files ending in `.zsh` get loaded into your
  environment.
- **topic/path.zsh**: Any file named `path.zsh` is loaded first and is
  expected to setup `$PATH` or similar.
- **topic/completion.zsh**: Any file named `completion.zsh` is loaded
  last and is expected to setup autocomplete.
- **topic/install.sh**: Any file named `install.sh` is executed when you run `script/install`. To avoid being loaded automatically, its extension is `.sh`, not `.zsh`.
- **topic/\*.symlink**: Any file ending in `*.symlink` gets symlinked into
  your `$HOME`. This is so you can keep all of those versioned in your dotfiles
  but still keep those autoloaded files in your home directory. These get
  symlinked in when you run `script/bootstrap`.

## install

Run this:

```sh
git clone git@github.com:jbwhit/dotfiles-setup.git ~/.dotfiles
cd ~/.dotfiles

# Maybe run: 
script/bootstrap
```

This will symlink the appropriate files in `.dotfiles` to your home directory.
Everything is configured and tweaked within `~/.dotfiles`.

The main file you'll want to change right off the bat is `zsh/zshrc.symlink`,
which sets up a few paths that'll be different on your particular machine.

`dot` is a simple script that installs some dependencies, sets sane macOS
defaults, and so on. Tweak this script, and occasionally run `dot` from
time to time to keep your environment fresh and up-to-date. You can find
this script in `bin/`.

## Setting up

Set up your `.ssh/config` file. This is a good start: http://nerderati.com/2011/03/17/simplify-your-life-with-an-ssh-config-file/

```
mkdir -p $HOME/.ssh
chmod 0700 $HOME/.ssh
```

Have a new key-pair for each new client laptop.

Learn tmux http://www.hamvocke.com/blog/a-quick-and-easy-guide-to-tmux/
http://www.starkandwayne.com/blog/iterm-and-tmux-sitting-in-a-tree/

## Your laptop will now have

 - brew installed
 - conda installed w/ reasonable starting packages
 - svds-style installed (automatically make Jupyter Notebooks have SVDS templating)
 - mplsvds installed (plots will use SVDS colors)
 - one-command functions to create minimal or template notebooks that query most up-to-date versions automatically
 - Extra command line tools 
     + pandoc
     + tmux
     + wget
     + grep
 - Applications (that you don't have to install separately from internet)
     + iTerm2
     + Sublime Text
     + Google Chrome
     + caffeine
     + flux
     + SourceTree
     + VLC


## Decommissioning 

 - Delete .ssh/
 - Remove installed applications
 - Empty trash


