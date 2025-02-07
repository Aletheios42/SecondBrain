**Tags:** #_Todo
#ToTag #ToLink 
- - -
**Duration**: 2-3 hours
**Prerequisites**: 
- VirtualBox installed
- ISO images for: Ubuntu Server, CentOS, and openSUSE

### Objectives
1. Compare kernel architectures across distributions
2. Analyze shell environments
3. Understand TTY and terminal differences
4. Compare system information across distributions

### Steps

1. Virtual Machine Setup
   ```bash
   # Create 3 VMs with following specs:
   - RAM: 2GB
   - CPU: 2 cores
   - Storage: 20GB
   # Install each distribution with minimal settings
   ```

2. Architecture Analysis
   ```bash
   # On each system, execute:
   uname -a > system_info.txt
   lsmod > kernel_modules.txt
   cat /proc/version >> system_info.txt
   dmesg | grep -i kernel > kernel_messages.txt
   ```

3. Shell Environment Comparison
   ```bash
   # Test different shells on each system
   chsh -l  # List available shells
   echo $SHELL  # Check current shell
   
   # For each available shell:
   # 1. Change to that shell
   chsh -s /bin/bash  # Example for bash
   
   # 2. Create test script
   echo 'echo $SHELL; env | grep "SHELL\|PATH"' > shell_test.sh
   chmod +x shell_test.sh
   ```

4. TTY Investigation
   ```bash
   # Switch between TTYs
   sudo chvt 1
   sudo chvt 2
   
   # Analyze TTY information
   w
   who
   ps aux | grep tty
   
   # Create report
   script tty_investigation.txt
   tty
   ls -l /dev/tty*
   ps -ef | grep tty
   exit
   ```

### Deliverables
1. Comparison table of kernel versions and modules
2. Shell environment analysis report
3. TTY mapping document

- - - 
## ***Sources:***
