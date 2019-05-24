# Install

Please make sure there is an `agda` executable in current path. It is not
listed in `depends` since you may not install it via `pacman`.

After installation, register and refer to standard library by

``` bash
$ echo "/usr/share/agda/lib/standard-library.agda-lib" >> ~/.agda/libraries
$ echo "standard-library" >> ~/.agda/defaults
```

# When Upgrade Agda

Remember to remove `~/.agda/libraries` and `~/.agda/defaults` first before upgrade `agda`.

If switched to a new version of Agda, please rebuild and reinstall this package.
Clean up the build environment by

``` bash
$ rm *.pkg.tar.xz `find . -name "*.agdai"`
```
