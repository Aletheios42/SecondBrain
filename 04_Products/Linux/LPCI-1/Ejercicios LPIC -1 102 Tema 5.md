**Tags:** #_Done 
#Linux  #ToLink 
- - -
# Guided Exercises
##### 1. Using rpm on a Red Hat Enterprise Linux system, how would you install the package file-roller-3.28.1-2.el7.x86_64.rpm showing a progress bar during the installation?
- R: rpm -ih file-roller-3.28.1-2.el7.x86_64.rpm 
##### 2. Using rpm, find out which package contains the file /etc/redhat-release.
- R:  rpm -qf /etc/redhat-release. La flag -qf significa queryfile
##### 3. How would you use yum to check for updates for all packages in the system?
- R: yum check-update
##### 4. Using zypper, how would you disable a repository called repo-extras?
- R: zypper modifyrepo -d repo-extras
##### 5. If you have a .repo file describing a new repository, where this file should be put so that it is recognized by DNF?
- R:  /etc/yum.repos.d/
# Explorational Exercises
##### 1. How would you use zypper to find out which package owns the file /usr/sbin/swapon?
- R:  zypper se --provides /usr/sbin/swapon
##### 2. How can you get a list of all installed packages in the system using dnf?
- R: dnf list --installed
##### 3. Using dnf, what is the command to add a repository located https://www.example.url/home:reponame.repo to the system?
- R:  dnf config-manager --add_repo https://www.example.url/home:reponame.repo
##### 4. How can you use zypper to check if the package unzip is installed?
- R: zypper se -i unzip
##### 5. Using yum, find out which package provides the file /bin/wget.
- R:  yum whatprovides /bin/wget

- - - 
## ***Sources:***