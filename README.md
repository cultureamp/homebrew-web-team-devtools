# Culture Amp web team Homebrew dev tools

A collection of helper scripts for system and application setup.

## Requirements

Install [Homebrew](https://brew.sh) on your Mac.

## Installation

```sh
brew tap cultureamp/web-team-devtools
```

## Scripts

### bootstrap-developer-system

Prepares our shared base development environment.

```sh
brew bootstrap-developer-system
```

This script:

- Installs the web team’s [shared
  dotfiles](https://github.com/cultureamp/web-team-dotfiles)
- Installs [asdf](https://asdf-vm.com) via Homebrew
- Installs the ruby and nodejs asdf plugins

### bootstrap-asdf

Installs asdf plugins and packages.

```sh
brew bootstrap-asdf
```

Run this script from within any directory with a `.tool-versions` file present,
and it:

- Installs the asdf plugin (if required) for each specified package
- If nodejs is specified, imports the release team’s keyring, so the nodejs file
  signatures can be verified
- Then runs `asdf install` to install all the specified packages

We typically use command in project `script/bootstrap` scripts, taken from our
[scripts to rule them all][scripts].

[scripts]: https://github.com/cultureamp/web-team-scripts-to-rule-them-all
