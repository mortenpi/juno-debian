# Juno launcher for Debian

These scripts can be used to package the launcher script for [Juno](https://junolab.org/), an Atom-base IDE for the [Julia language](https://julialang.org/), into a `.deb` package.

Built packages can be installed from the [~mortenpi/julia-meta](https://launchpad.net/~mortenpi/+archive/ubuntu/julia-meta) Launchpad repository:

```sh
```

## Building

Pre-requisite packages for building:

```sh
apt install devscripts debhelper
```

While in the `src/` directory:

* With the `DEBEMAIL` environment variable set, call `dch -v new-version-number` to update the changelog with a new version number.
* Call `debuild` to build the "binary" package.

For uploading to Launchpad:

* `debuild -S` to build a source package that can be pushed to Launchpad with `dput`.
* Run `debsign -k key-id sources-changes-file` on the `*_sources.changes` file to GPG sign it for upload.

## Helpful resources

* https://askubuntu.com/a/91616/397422
