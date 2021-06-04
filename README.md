# cleanit

## Overview

Cleanit moves files older than 20 days (default) from a directory (default ~/Downloads) to another directory (default ~/.Trash).

```sh
Usage:  cleanit [ -f ] [ -d ] [ -t ][ -h ]
    -f target-directory (~/Downloads as default) 
    -d (Default is 20) Set days to indicate the maximum days to keep files. 
    -t (default is ~/.Trash) Set the directory where you want files to move to. 
    -h Show help
    -v Show version
```

## Prerequisite

For cron job, you need to allow BOTH of Terminal.app and /bin/bash Full Disk permissions in the security settings. ![security](https://raw.githubusercontent.com/shinokada/cleanit/main/images/bash-full-disk-access.png)

When you select /bin/bash, you need to show hidden files by `SHIFT+CMD+.`.

## Installation

### Homebrew

```sh
brew tap shinokada/cleanit && brew install cleanit
```

### Awesome

The `awesome` is a simple script package manager. It creates the `~/awesome` directory and the `~/bin` directory if they don't exist. When you install a script package in the `~/awesome` directory and, it creates a symlink in the `~/bin` directory.

Install [`awesome`](https://github.com/shinokada/awesome) first:

```sh
curl -s https://raw.githubusercontent.com/shinokada/awesome/main/install | bash -s install
```

Then install `cleanit`:

```sh
awesome install cleanit
```

## Uninstallation

### Homebrew unistall

```sh
brew uninstall cleanit
```

### Awesome unistall

```sh
awesome uninstall cleanit
```

## Examples

Move files older than 20 days in ~/Downloads to ~/.Trash

```sh
cleanit
```

Move files older than 10 days in ~/Mydir to ~/.Trash

```sh
cleanit -d 10 -f ~/Mydir
```

Move files older than 5 days in ~/Mydir to ~/Anotherdir

```sh
cleanit -f ~/Mydir -d 5 -t ~/Anotherdir
```

You can clean up the Trash directory.

```sh
cleanit -d 30 -f trash
```

This will remove files older than 30 days from `~.Trash` directory

```sh
cleanit -c -o 10 -m 0 -d 30
```

This will set cronjob removing files older than 30 days (default 20 days) everyday at 8:00 am. The default days for Downloads directory is fixed at 20 days.

Remove a cron job:

```sh
cleanit -r
```

## Author

Shinichi Okada

## Licence

Please see license.txt.
