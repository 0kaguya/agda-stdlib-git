## Install

Make sure you have the `agda` binary in your path. 

After installed, you may want to register and make default the stdlib:

``` bash
$ if [ ! -d ~/.agda ]; then mkdir ~/.agda; fi
$ echo "/usr/share/agda/lib/standard-library.agda-lib" >> ~/.agda/libraries
$ echo "standard-library" >> ~/.agda/defaults
```

## Upgrade

You need reinstall this package after modifying the main agda program.
