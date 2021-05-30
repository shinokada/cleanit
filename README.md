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

- In the security settings, allow Terminal app Full Disk permissions. ![security](https://raw.githubusercontent.com/shinokada/cleanit/main/images/bash-full-disk-access.png)


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
cleanit -c -o 8 -m 0 -d 30
```

This will set cronjob removing files older than 30 days (default 20 days) everyday at 8:00 am. The default days for Downloads directory is fixed at 20 days.

## Author

Shinichi Okada

## Licence

Please see license.txt.
