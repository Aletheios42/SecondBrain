**Tags:** #_Done 
#Linux  #ToLink 
- - -
# Guided Exercises
##### 1. What command would you use to determine what Xorg extensions are available on a system?
- R:  xdpyinfo
##### 2. You have just received a brand new 10-button mouse for your computer, however it will require extra configuration in order to get all of the buttons to function properly. Without modifying the rest of the X server configuration, what directory would you use to create a new configuration file for this mouse, and what specific configuration section would be used in this file?
- R: /etc/X11/xorg.conf.d/ and the seccion is input device
##### 3. What component of a Linux installation is responsible for keeping an X server running?
- R: The display manager
##### 4. What command line switch is used with the X command to create a new xorg.conf configuration file?
- R: -configure

# Explorational Exercises
##### 1. What would the contents of the DISPLAY environment variable be on a system named lab01 using a single display configuration? Assume that the DISPLAY environment variable is being viewed in a terminal emulator on the third independent screen.
- R:  $ echo $DISPLAY
	lab01:0.2
##### 2. What command can be used to create a keyboard configuration file for use by the X Window System?
- R:  localectl
##### 3. On a typical Linux installation a user can switch to a virtual terminal by pressing the Ctrl + Alt + F1 - F6 keys on a keyboard. You have been asked to set up a kiosk system with a graphical interface and need this feature disabled to prevent unauthorized tampering with the system. You decide to create a /etc/X11/xorg.conf.d/10-kiosk.conf configuration file. Using a ServerFlags section (which is used to set global Xorg options on the server), what option would need to be specified? Review the xorg(1) man page to locate the option.
- R:   Section "ServerFlags"
Option
 "DontVTSwitch"
 "True"
EndSection

- - - 
## ***Sources:***