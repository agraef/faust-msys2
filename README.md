
Faust msys2 mingw builds
========================

These provide 32 and 64 bit builds of Grame's [Faust][0] for Windows.
You'll need [msys2](http://www.msys2.org/) to use these. Install msys2
following the instructions on the msys2 website, then install a basic
development environment like so:

    pacman -S --needed base-devel mingw-w64-i686-toolchain mingw-w64-x86_64-toolchain git

This should give you a fairly complete i686/x86_64 bit build environment
including gcc and the usual development tools, which can then be used to build
Faust modules on Windows after installing the packages provided here.

Both 32 bit and 64 packages are available which can be installed using
`pacman` as usual:

    pacman -U mingw-w64-*-faust-git-*.pkg.tar.xz

You can also [build the packages][1] yourself using the PKGBUILD in the
faust-git subdirectory. This is pretty much the same PKGBUILD as the one
available in the [AUR][2], massaged so that it will create proper msys2 mingw
packages allowing both 32 and 64 bit versions of the package to be installed
at the same time.

Note that this implies that the auxiliary content of the package (most
notably, the syntax highlighting files) will also be installed under the
mingw32 and mingw64 prefixes, respectively. Thus you'll have to copy them over
(e.g., from mingw32/usr/share/emacs/site-lisp to usr/share/emacs/site-lisp in
the case of the Emacs Faust mode) if you want to use these.

[0]: http://faust.grame.fr/
[1]: https://github.com/msys2/msys2/wiki/Creating-packages
[2]: https://aur.archlinux.org/packages/faust-git/
