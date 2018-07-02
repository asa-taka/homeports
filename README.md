# homeports

Now WIP

## Installation

- `~/.homeports` is where `homeports` is installed to
  - It's customizable by `$HOMEPORTS_DIR`
- `~/.homeports/home` is for your $HOME contents preserver

### What's the Home Repository

Home repository contains the subtree of your $HOME which your want to share by your devices.
Typically, it would contain stuffs like below...

```
$ tree -a
.
├── .bash_profile
└── bin
    └── my-script
```

### When you already have your $HOME repository

```sh
# Install this tool
git clone https://github.com/asa-taka/homeports ~/.homeports

# A git repository preserving subset of Your $HOME
git clone https://github.com/<you>/myhome ~/.homeports/home

# locate `homeports` on your $PATH
ln -s ~/.homeports/homeports /usr/local/bin # or your desiered location
```

### When you don't have home repository

```sh
# Install this tool
git clone https://github.com/asa-taka/homeports ~/.homeports

# Create new directory
# later, it should be a git repository
mkdir ~/.homeports/home

# locate `homeports` on your $PATH
ln -s ~/.homeports/homeports /usr/local/bin # or your desiered location
```

To setup the new directory into a git repository, `homeports sh` is useful to enter there.

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