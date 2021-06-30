# Cleanit

## Overview

Cleanit cleanup your `~/Downloads` and `~/.Trash` directory, and set the cleanup schedule on your MacOS.

Cleanit moves files older than 20 days (default) from a directory (default ~/Downloads) to another directory (default ~/.Trash).

## Usage

```sh
cleanit [-f <dir>][-t <dir>][-D <number>]
cleanit cron -H <hour> -M <minute> [-D <number>]
cleanit downloads [-D <number>]
cleanit trash [-D <number>]
cleanit -r
```

## Options

```sh
-f  target-directory [default: ~/Download as default]
-t  Set the directory where you want files to move to. [default: ~/.Trash]
-r  Remove a cronjob
-D  Set days to indicate the maximum days to keep files. [default: 20]
-H  Set the hour to a cronjob
-M  Set the min to a cronjob
-h Show help
-v Show version
```

## Prerequisite

For cron job, you need to allow **BOTH** of Terminal.app and `/bin/bash` Full Disk permissions in the security settings.

Find out your bash location first:

```sh
which bash
```

When you select /bin/bash, you need to show hidden files by `SHIFT+CMD+.`.

![security](https://raw.githubusercontent.com/shinokada/cleanit/main/images/bash-full-disk-access.png)

Apple x86_64

![bin/bash](https://raw.githubusercontent.com/shinokada/cleanit/main/images/bin-bash.png)

Apple M1 chip/ARM64

![bin/bash](https://raw.githubusercontent.com/shinokada/cleanit/main/images/homebrew-bash.png)

Restart your Mac.

## Installation

### Using Homebrew

```sh
brew tap shinokada/cleanit && brew install cleanit
```

### Using Awesome Package Manager

After installing the [Awesome script package manager](https://github.com/shinokada/awesome):

```sh
awesome install shinokada/cleanit
brew install terminal-notifier
brew install bash
```

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
cleanit
```

Clean up Downloads

```sh
cleanit downloads
# or
cleanit -f downloads
```

Clean up Trash

```sh
cleanit trash
# or
cleanit -f trash
```

Move files older than 10 days in ~/Mydir to ~/.Trash

```sh
cleanit -D 10 -f ~/Mydir
```

Move files older than 5 days in ~/Mydir to ~/Anotherdir

```sh
cleanit -D 5 -f ~/Mydir -t ~/Anotherdir
```

You can clean up the Trash directory.

```sh
cleanit -D 20 trash
cleanit -D 20 -f trash
```

Cleanup the Downloads directory.

```sh
cleanit -D 10 downloads
cleanit -D 10 -f downloads
```

This will remove files older than 30 days from `~.Trash` directory

```sh
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
