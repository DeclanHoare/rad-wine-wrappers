# RAD WINE Wrappers

The RAD WINE Wrappers are a set of automatically generated shell scripts
which run RAD Studio's command line tools under WINE.

## Why?

RAD Studio is designed for cross-platform application development and as
a result it can be rather useful for porting Windows software. However,
it is only designed for use on Windows. Some parts of it work fine under
WINE, but using WINE to run tools is obnoxious to include in your build
system. These scripts exist to make the tools included in RAD Studio
look like regular native tools to your build system.

## Building

The RAD Wine Wrappers are generated using autotools. However, you will
need the original RAD Studio installer as a "source" file first.

Download it from:
http://altd.embarcadero.com/download/radstudio/10.1/radstudio10_1_upd2_esd.exe
and place either it or a symlink to it in the "src" directory.

You will also need to run
`autoreconf -i`
to generate a configure script.

Now you're ready to run the classic
`./configure; make`
as yourself and then
`make install`
as root.

This produces a package called "radstudio", which contains both the
Wrappers and some of the files from RAD Studio itself.
