This is a quick guide to cross compile a MSDOS binary.
------------------------------------------------------

First get a cross compiler:

- git clone https://github.com/andrewwutw/build-djgpp.git

(or just grab a prebuilt one from the GitHub page)

Get allegro-4.2:

- git clone https://github.com/1oom-fork/allegro4

"Fix" it for djgpp:

- ./fix.sh djgpp

Edit xmake.sh and check that the paths and compiler name are correct:

XC_PATH=/<djgpp_path>/i586-pc-msdosdjgpp/bin:/<djgpp_path>/bin
XPREFIX=i586-pc-msdosdjgpp-
INSTALL_BASE=/<djgpp_path>/i586-pc-msdosdjgpp

Build and install:

- ./xmake.sh depend
- ./xmake.sh lib -j 3
- sudo ./xmake.sh install
