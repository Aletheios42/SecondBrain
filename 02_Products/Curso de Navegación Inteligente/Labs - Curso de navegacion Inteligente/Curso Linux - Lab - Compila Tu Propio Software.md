**Tags:** #_Todo
#ToTag #ToLink 
- - -

Download, Extract, Compile, and Install Your Software
Download your compressed source code using a method such as wget:
$ wget https://invisible-mirror.net/archives/lynx/tarballs/lynx2.8.9rel.1.tar.gz
Extract the source code from the compressed archive:
$ tar zxvf lynx2.8.9rel.1.tar.gz
Change directory into the lynx source tree created by the extracting process:
$ cd lynx2.8.9rel.1
Before running configure, take a few minutes to look for and read the README file that always exists in source
code trees. This file has valuable instructions and information about the source code and installation instructions.
This README file refers you to the INSTALLATION file that describes installation options. For demonstration
purposes, I’m accepting all the defaults and simply running the configure script. If all dependencies are met, then
the configuration checks will go without error, create the makefile, and then drop you back at your shell prompt.
This process can take a few minutes to complete.
$ ./configure
Both configure scripts failed with the following error:
checking for screen type... curses
checking for specific curses-directory... no
checking for extra include directories... no
checking if we have identified curses headers... none
configure: error: No curses header-files found
When you encounter errors, the configure script stops but keeps its place so that as you satisfy dependencies, you
may continue where you left off by running the configure script again. To satisfy the current dependency, I
installed the ncurses-devel package on the CentOS system. The configure script completed successfully. For the
Ubuntu system, I installed the lib32ncurses-dev package and the configure script completed successfully.According to the INSTALLATION file, you now must run the make command to compile the sources. This
process will take a few minutes to complete:
$ make
After satisfying the failed dependencies in the configure script, both compilations proceeded to successful
completion. To install lynx to its proper location and set the correct permissions, run sudo make install:
$ sudo make install
/bin/sh -c "P=`echo lynx|sed 's,x,x,'`; \
if test -f /usr/local/bin/$P ; then \
mv -f /usr/local/bin/$P /usr/local/bin/$P.old; fi"
/usr/bin/install -c lynx /usr/local/bin/`echo lynx|sed 's,x,x,'`
/usr/bin/install -c -m 644 ./lynx.man /usr/local/share/man/man1/`echo lynx|sed
's,x,x,'`.1
** installing ./lynx.cfg as /usr/local/etc/lynx.cfg
** installing ./samples/lynx.lss as /usr/local/etc/lynx.lss
Use make install-help to install the help-files
Use make install-doc to install extra documentation files
At this point, most instructions advise you to run make clean to remove all of the object code and other
temporary files from your system:
$ make clean
rm -f WWW/Library/*/*.[aoib]
rm -f WWW/Library/*/.created
cd ./WWW/Library/Implementation && make DESTDIR="" CC="gcc" clean
make[1]: Entering directory '/home/khess/lynx2.8.9rel.1/WWW/Library/Implementation'
rm -f core *.core *.leaks *.[oi] *.bak tags TAGS
rm -f dtd_util
rm -f ./*.o
make[1]: Leaving directory '/home/khess/lynx2.8.9rel.1/WWW/Library/Implementation'
cd ./src && make DESTDIR="" CC="gcc" clean
make[1]: Entering directory '/home/khess/lynx2.8.9rel.1/src'
rm -f lynx core *.core *.leaks *.i *.o *.bak tags TAGS test_*
cd chrtrans && make DESTDIR="" CC="gcc" clean
make[2]: Entering directory '/home/khess/lynx2.8.9rel.1/src/chrtrans'
rm -f makeuctb *.o *uni.h *uni2.h *.i
make[2]: Leaving directory '/home/khess/lynx2.8.9rel.1/src/chrtrans'
make[1]: Leaving directory '/home/khess/lynx2.8.9rel.1/src'
rm -f *.b ./src/lynx *.leaks cfg_defs.h LYHelp.h lint.*
rm -f help_files.sed
rm -f core *.core
It’s a matter of preference to run this command. If you need to remove compiled software from your system, the
next section steps you through the process of doing so.
Uninstalling a Source-Installed Software Package
If your source trees exist with your original makefile intact, you can uninstall a package quite easily but you must
have the makefile to do so. If you don’t want to keep all of your source trees on your system for every compiled
program, make a backup of the makefile such as copying it to a backup directory with the name
makefile.lynx289r1 or similar. The makefile must be in your current directory when uninstalling:
$ sudo make uninstall
rm -f /usr/local/bin/`echo lynx|sed 's,x,x,'`
rm -f /usr/local/share/man/man1/`echo lynx|sed 's,x,x,'`.1rm -f /usr/local/etc/lynx.cfg
rm -f /usr/local/etc/lynx.lss
/bin/sh -c 'if test -d "/usr/local/share/lynx_help" ; then \
WD=`cd "/usr/local/share/lynx_help" && pwd` ; \
TAIL=`basename "/usr/local/share/lynx_help"` ; \
HEAD=`echo "$WD"|sed -e "s,/${TAIL}$,,"` ; \
test "x$WD" != "x$HEAD" && rm -rf "/usr/local/share/lynx_help"; \
fi'
/bin/sh -c 'if test -d "/usr/local/share/lynx_doc" ; then \
WD=`cd "/usr/local/share/lynx_doc" && pwd` ; \
TAIL=`basename "/usr/local/share/lynx_doc"` ; \
HEAD=`echo "$WD"|sed -e "s,/${TAIL}$,,"` ; \
test "x$WD" != "x$HEAD" && rm -rf "/usr/local/share/lynx_doc"; \
fi'
/bin/sh -c 'if test -d "/usr/local/share/lynx_help" ; then \
WD=`cd "/usr/local/share/lynx_help" && pwd` ; \
TAIL=`basename "/usr/local/share/lynx_help"` ; \
HEAD=`echo "$WD"|sed -e "s,/'${TAIL}'$,,"` ; \
test "x$WD" != "x$HEAD" ; \
cd "/usr/local/share/lynx_help" && rm -f COPYING COPYHEADER ; \
fi'
If you don’t have your makefile or it isn’t in your current directory, you receive the following error:
$ sudo make uninstall
make: *** No rule to make target 'uninstall'.
Stop.
You can re-create the makefile if you extract the same version of the source tree that you previously used and can
remember your configure options. Otherwise, you can use the above uninstall results to guide you in uninstalling
manually.
- - - 
## ***Sources:***