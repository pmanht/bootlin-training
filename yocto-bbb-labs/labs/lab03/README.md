#create file bb
mkdir poky/meta/recipes-extended/ninvaders
vim poky/meta/recipes-extended/ninvaders/ninvaders_0.1.1.bb

# file contents
SUMMARY = "ninvaders program"
DESCRIPTION = "ninvaders is an ncurses version of the Invaders video game. The native installation packages are customized for integration with Asciiville."
HOMEPAGE = "https://ninvaders.sourceforge.net"
SECTION = "ninvaders"
LICENSE = "GPL-2.0-or-later"
SRC_URI = "https://sourceforge.net/projects/ninvaders/files/ninvaders/0.1.1/ninvaders-0.1.1.tar.gz"
SRC_URI[md5sum] = "97b2c3fb082241ab5c56ab728522622b"
LIC_FILES_CHKSUM = "file://nInvaders.c;beginline=1;endline=22;md5=f764774d93e5f81453db530f1b810b13"

DEPENDS += "ncurses"
#EXTRA_OEMAKE += "CC='${CC}' CFLAGS='${CFLAGS} -fcommon'"
EXTRA_OEMAKE:append = "CC='${CC}' CFLAGS='${CFLAGS} -fcommon'"

do_compile() {
        oe_runmake
}

do_install() {
        install -d ${D}${bindir}
        install -m 0755 nInvaders ${D}${bindir}
}

