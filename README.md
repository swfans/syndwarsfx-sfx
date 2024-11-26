# swars-sfx

Sound samples source for Syndicate Wars Port.

## About

**Syndicate Wars Port**, alternative binary for the classic Bullfrog game.

Alongside fixes to the game executable code, an updated set of assets is
required to use the full potential of the code fixes.

This repository contains the original sound samples and speeches developed by
Bullfrog, with additional fixes applied to the files by fan community.

## Installation from a release

Download the release `swars-sfx-*.zip` file. Copy the extracted
`SOUND` folder to a previous Syndicate Wars Port installation,
replacing the existing files.

### General building instructions

To build **Syndicate Wars SFX**, use the following steps:

1. download [sndbanker](https://github.com/swfans/sndbanker/releases/),
   place the binary in `swars-sfx/bin` or any folder included in `PATH` env var.
2. go into the directory with `swars-sfx` source release
3. do `autoreconf -if` to create build scripts from templates
4. do `./configure` to make the build scripts find required dependencies
5. do `make` to build release versions of data files
6. do `make install` to copy the files into `swars` installation folder

You should now have the latest DAT sound banks in your installation folder.

#### Build example - Ubuntu 20.04 64-bit

Here are specific commands required to build the sfx on Ubuntu linux.

Download the `swars-sfx` source release, and extract it somewhere.

Also download latest release of the [sndbanker](https://github.com/swfans/sndbanker/releases/),
and extract the binary into `bin` sub-folder of the place with `swars-sfx`.
If you've downloaded the `.zip` to `swars-sfx` folder, you can just go there and run:

```
unzip -j -d ./bin/ sndbanker-*-ubuntu.zip
```

Being still in the `swars-sfx` folder, generate build scripts from templates using
autotools:

```
autoreconf -ivf
```

Next, proceed with the build steps; we will do that in a separate folder.

```
mkdir -p release; cd release
../configure
make V=1
```

The `V=1` variable makes `make` print each command it executes, which makes
diagnosing issues easier.

You can use `make install` to add the files to your installation, or copy
them to a new folder from which you may copy them manually.

To copy output files to a `pkg` folder, creating  proper sub-folders for
release, use:


```
make V=1 DESTDIR=$PWD/pkg install
```

That's it, now you have the DAT sound banks ready.

## Done

That's all. See more documentation in [Syndicate Wars Port repo](https://github.com/swfans/swars).
