# cleanit

## Overview

Cleanit moves files older than 20 days (default) from a directory (default ~/Downloads) to another directory (default ~/.Trash).

```sh
Usage:  cleanit [ -f ] [ -d ] [ -t ][ -h ]
    -f target-directory (~/Download as default) 
    -d (Default is 20) Set days to indicate the maximum days to keep files. 
    -t (default is ~/.Trash) Set the directory where you want files to move to. 
    -h Show help
    -v Show version
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


## Author

Shinichi Okada

## Licence

Please see license.txt.
