**Tags:** #_Done 
#Linux  #ToLink 
- - -
# Guided Exercises
##### 1. A new printer was just installed on a local workstation named office-mgr. What command could be used to set this printer as the default for this workstation?
- R: lpoptions -d office-mgr
##### 2. Which command and option would be used to determine what printers are available for printing from a workstation?
- R: lpstat -p
##### 3. Using the cancel command, how would you remove a print job with ID 15 that is stuck in the queue for the printer named office-mgr?
- R:  cancel office-mgr-15
##### 4. You have a print job destined for a printer that does not have enough paper to print the full file. What command would you use to move the print job with ID 2 queued to print on the FRONT-DESK printer over to the print queue for the ACCOUNTING-LASERJET printer?
- R:   sudo lpmove FRONT-DESK-2 ACCOUNTING-LASERJET

# Explorational Exercises
###### Using your distribution’s package manager, install the cups and the printer-driver-cups-pdf packages. Note that if you are using a Red Hat based distribution (such as Fedora) the CUPS PDF driver is called cups-pdf. Also install the cups-client package to utilize the System V style printing commands We will use these packages to practice managing a CUPS printer without physically installing a real printer.
##### 1. Verify that the CUPS daemon is running, then verify that the PDF printer is enabled and set to the default.
 - R:  lpstat -p -d
##### 2. Run a command that will print the /etc/services file. You should now have a directory named PDF within your home directory.
- R:  lp -d PDF /etc/services
##### 3. Use a command that will only disable the printer, then run a separate command that shows all status information to verify that the PDF printer is disabled. Then try to print a copy of your /etc/fstab file. What happens?
- R:  sudo cupsdisable PDF
 scheduler is running
##### 4. Now try to print a copy of the /etc/fstab file to the PDF printer. What happens?
- R: After attempting the command lp -d PDF /etc/fstab you should get output showing the job ID information. However, if you check the PDF folder in your home directory, the new file is not there. You can then check the print queue with the lpstat -o command, and you will find your job listed there.
##### 5. Cancel the print job, then remove the PDF printer.
- R:  cancel PDF-4

- - - 
## ***Sources:***