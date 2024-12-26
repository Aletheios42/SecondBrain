**Tags:** #_Done 
#Linux  #ToLink 
- - -
# Guided Exercises
##### 1. What is the command to install a package named package.deb using dpkg?
- R: dkpg -i package.deb
##### 2. Using dpkg-query, find which package contains a file named 7zr.1.gz.
- R: dkpg-query -S 7zr.1.gz
##### 3. Can you remove a package called unzip from the system using dpkg -r unzip if the package file-roller depends on it? If not, what would be the correct way to do it?
-R : primero borras la dependencia asi dkpg -r file-roller y luego el paquete asi dkpg -r unzip
##### 4. Using apt-file, how can you find out which package contains the file unrar?
- R: apt-file search /usr/bin/unrar
##### 5. Using apt-cache, what is the command to show information for the package gimp?
- R:  apt-cache show gimp

# Explorational Exercises
##### 1. Consider a repository with Debian source packages for the xenial distribution, hosted at http://us.archive.ubuntu.com/ubuntu/ and with packages for the universe component. What would be the corresponding line to be added to /etc/apt/sources.list?
- R: La línea puede ubicarse en:
/etc/apt/sources.list o en /etc/apt/sources.list.d/ con extensión .list   
la sitaxix es : deb-src [URL] [distribución] [componentes] asi que:
deb-src http://us.archive.ubuntu.com/ubuntu/ xenial universe
##### 2. While compiling a program, you come across an error message complaining that the header file zzip-io.h is not present in your system. How can you find out which package provides that file?
- R:  apt-file search zzip-io.h
##### 3. How can you ignore a dependency warning and remove a package using dpkg, even if there are packages that depend on it in the system?
- R: dpkg --force-depends -r/-p nombre_paquete  la diferencia entre remove y purge es que purge ademas borra los archivos de configuracion
##### 4. How can you get more information about a package called midori using apt?
- R: apt-cache show midori
##### 5. Before installing or updating packages with apt, which command should be used to ensure that the package index is up-to-date?
- R: apt-update para dejar el listado de depndencias actualizado en el archivo /etc/apt/sources.list en el directorio /etc/apt/sources.list.d/ .
- - - 
## ***Sources:***