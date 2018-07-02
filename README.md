# homeports

Now WIP

## Installation

### When you already have home repository

```sh
git clone https://github.com/asa-taka/homeports ~/.homeports
git clone https://github.com/<you>/myhome ~/.homeports/home
ln -s ~/.homeports/homeports /usr/local/bin # or your desiered location
```

### You don't have home repository

```sh
git clone https://github.com/asa-taka/homeports ~/.homeports
mkdir ~/.homeports/home
ln -s ~/.homeports/homeports /usr/local/bin # or your desiered location
```

### Tips

You can select other location than `~/.homeports` to clone this repository.
If you do so, set `HOMEPORTS_DIR` properly for the path you installed.

## Command Reference

```
$ homeports help
Management user home
Usage: homeports <command> ...

Entry Management Commands:
  add <file> [<file> ...]
          : register files to be under homeports management (with commit)
  delink  : replace all symlinks into reguler files
  edit    : open homeports directory by HOMEPORTS_EDTOR=${HP_EDITOR}
  link    : create symlinks
  links   : list all symlinks
  list    : list all registered entries
  rm [<entry> ...]
          : unregister the entry (with commit)
  unlink  : remove all symlinks

Repository Management Commands:
  commit  : commit changes
  pull    : pull updates from remote
  push    : push updates to remote
  remote  : show remote information

Utility Commands:
  doctor  : check dependencies
  env     : show configurable ENVs
  find    : find all links pointing the repository under $HOME
  help    : show this help
  init    : clean all registered contents
  log     : show commit log
  sh      : enter homeports shell by HOMEPORTS_SHELL=${HP_SHELL}
  update  : update homeports
```