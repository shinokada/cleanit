# cleanit

## Overview

Cleanit cleanup your `~/Downloads` and `~/.Trash` directory, and set the cleanup schedule.

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

The cron job works for macOS only.

For cron job, you need to allow **BOTH** of Terminal.app and `/bin/bash` Full Disk permissions in the security settings. ![security](https://raw.githubusercontent.com/shinokada/cleanit/main/images/bash-full-disk-access.png)

![bin/bash](https://raw.githubusercontent.com/shinokada/cleanit/main/images/bin-bash.png)


When you select /bin/bash, you need to show hidden files by `SHIFT+CMD+.`.

- coreutils

Install `coreutils` on macOS:

```sh
brew install coreutils
```

Install it on Ubuntu:

```sh
apt install coreutils
```

## Installation

### macOS x86_64/Linux using Homebrew

```sh
brew tap shinokada/cleanit && brew install cleanit
```

### macOS M1 chip/arm64

Install using Awesome package manager. See the next section.

### Using [Awesome Package Manager](https://github.com/shinokada/awesome) for macOS/Linux

After installing the [Awesome script package manager](https://github.com/shinokada/awesome):

```sh
awesome install shinokada/cleanit
brew install terminal-notifier
brew install bash
brew install coreutils
```

Linux user must specify your Downloads directory and Trash directory using `-f /path/to/Downloads` and `-t /path/to/Trash`.

## Uninstallation

### Homebrew unistall

```sh
brew uninstall cleanit
```

### Awesome unistall

```sh
awesome rm cleanit
```

## Examples

Move files older than 20 days in ~/Downloads to ~/.Trash

```sh
# macOS
cleanit
# Linux
cleanit -f /path/to/dir -t /path/to/trash
```

Move files older than 10 days in ~/Mydir to ~/.Trash

```sh
# macOS
cleanit -D 10 -f ~/Mydir
# Linux
cleanit -D 10 -f '/path/to/dir' -t '/path/to/trash'
```

Move files older than 5 days in ~/Mydir to ~/Anotherdir

```sh
cleanit -D 5 -f ~/Mydir -t ~/Anotherdir
```

You can clean up the Trash directory.

```sh
# macOS
cleanit -D 30 -f trash
# Linux
cleanit -D 30 -f /path/to/trash
```

This will remove files older than 30 days from `~.Trash` directory

```sh
# only macOS
cleanit cron -H 10 -M 0 -D 30
```

This will set cronjob removing files older than 30 days (default 20 days) everyday at 8:00 am. The default days for Downloads directory is fixed at 20 days.

Remove a cron job:

```sh
cleanit -r
```

## Author

Shinichi Okada

## License

MIT License

Copyright (c) 2021 Shinichi Okada

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
