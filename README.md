# usbmuxd2-aur-repo
I do this repo because at this hour I don't want waste more time on reading how to add a AUR package

# This isn't my package
There is link to this original package: https://aur.archlinux.org/packages/usbmuxd2-git
I only fixed it because this package don't wanted to build. The problem was that autogen.sh was building project with GCC and author said that this program needs to be builded with clang.
So I changed a 27 line in PKGBUILD.

From:
`CC=clang ./autogen.sh --sbindir=/usr/bin`
To:
`./autogen.sh CC=clang CXX=clang++ --sbindir=/usr/bin`
And now it works
