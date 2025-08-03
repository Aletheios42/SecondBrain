**Tags:** #_Todo
#ToTag #ToLink 
- - -

# Guided Exercises
##### 1. What CPU extensions are necessary on an x86 based hardware platform that will run fully virtualized guests?
- R: VT-x for Intel CPUs or AMD-V for AMD CPUs
##### 2. A mission-critical server installation that will require the fastest performance will likely use what type of virtualization?
- R: An operating system that makes use of paravirtualization, such as Xen, as the guest operating system can make better use of hardware resources available to it through the use of software drivers designed to work with the hypervisor.
##### . 3. Two virtual machines that have been cloned from the same template and that utilize D-Bus are performing erratically. They both have separate hostnames and network configuration settings. What command would be used to determine if each of the virtual machines have different D-Bus Machine IDs?
- R: dbus-uuidgen --get
# Explorational Exercises
##### 1. Run the following command to see if your system already has CPU extensions enabled to run a virtual machine (your results may vary depending on your CPU): grep --color -E "vmx|svm" /proc/cpuinfo Depending on the output, you may have vmx highlighted (for Intel VT-x enabled CPU’s) or svm highlighted (for AMD SVM enabled CPU’s). Should you get no results, consult your BIOS or UEFI firmware instructions on how to enable virtualization for your processor.
- R: done..
##### 2. If your processor supports virtualizations, seek out your distribution’s documentation for running a KVM hypervisor.
◦ Install the necessary packages to run a KVM hypervisor.
◦ If you are using a graphical desktop environment, it is recommended to also install the virt-manager application which is a graphical front-end that can be used on a KVM installation. This will aid in virtual machine installations and management.
◦ Download a Linux distribution ISO image of your choice, and following your distribution’s documentation create a new virtual machine using this ISO.
- R: TODO
- - - 
## ***Sources:***