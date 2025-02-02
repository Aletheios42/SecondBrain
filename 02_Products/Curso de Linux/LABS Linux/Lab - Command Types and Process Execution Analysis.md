**Tags:** #_Todo
#ToTag #ToLink 

**Prerequisites**: 
- Linux VM (Ubuntu or CentOS)
- strace installed
- Root access

### Objectives
1. Differentiate between built-in commands, aliases, and external binaries
2. Analyze process creation and execution using strace
3. Understand shell process hierarchy
4. Compare execution paths of different command types

### Part 1: Command Type Analysis

1. Setup Environment
   ```bash
   # Install necessary tools
   sudo apt-get install strace
   # or for CentOS
   sudo yum install strace
   
   # Create test directory
   mkdir ~/cmdtest
   cd ~/cmdtest
   ```

2. Create Test Commands
   ```bash
   # Create a simple external command
   cat << 'EOF' > mycmd.sh
   #!/bin/bash
   echo "This is an external command"
   sleep 1
   EOF
   chmod +x mycmd.sh
   
   # Create aliases
   alias mycmd_alias='echo "This is an alias command"'
   alias ls_custom='ls -lah --color=auto'
   
   # Document path
   echo $PATH > path_before.txt
   export PATH=$PATH:$HOME/cmdtest
   echo $PATH > path_after.txt
   ```

### Part 2: Process Tracing

1. Create Tracing Script
   ```bash
   cat << 'EOF' > trace_commands.sh
   #!/bin/bash
   
   echo "=== Testing built-in command ==="
   strace -f -e trace=process pwd 2> pwd_trace.txt
   
   echo "=== Testing alias ==="
   strace -f -e trace=process ls_custom 2> alias_trace.txt
   
   echo "=== Testing external command ==="
   strace -f -e trace=process ./mycmd.sh 2> external_trace.txt
   EOF
   chmod +x trace_commands.sh
   ```

2. Command Type Analysis
   ```bash
   # Create analysis script
   cat << 'EOF' > analyze_commands.sh
   #!/bin/bash
   
   echo "=== Command Type Analysis ==="
   
   commands=("pwd" "cd" "ls" "echo" "./mycmd.sh" "ls_custom")
   
   for cmd in "${commands[@]}"; do
     echo -n "$cmd is "
     type -a "$cmd" 2>/dev/null || echo "not found"
     
     if type -t "$cmd" >/dev/null 2>&1; then
       case $(type -t "$cmd") in
         "builtin")
           echo "  -> Executes in shell process"
           ;;
         "file")
           echo "  -> Creates new process"
           ;;
         "alias")
           echo "  -> Expands in shell"
           ;;
       esac
     fi
     echo
   done
   EOF
   chmod +x analyze_commands.sh
   ```

### Part 3: Shell Process Hierarchy

1. Create Process Tree Script
   ```bash
   cat << 'EOF' > process_tree.sh
   #!/bin/bash
   
   echo "=== Current Shell Process Tree ==="
   ps f -o pid,ppid,cmd
   
   echo -e "\n=== Execute External Command ==="
   ./mycmd.sh &
   sleep 0.1
   ps f -o pid,ppid,cmd
   
   echo -e "\n=== Execute Built-in Command ==="
   pwd &
   sleep 0.1
   ps f -o pid,ppid,cmd
   EOF
   chmod +x process_tree.sh
   ```

### Part 4: Performance Analysis

2. Create Timing Script
   ```bash
   cat << 'EOF' > time_execution.sh
   #!/bin/bash
   
   echo "=== Timing Analysis ==="
   
   # Time built-in command
   time -p pwd > /dev/null
   
   # Time alias
   time -p ls_custom > /dev/null
   
   # Time external command
   time -p ./mycmd.sh > /dev/null
   EOF
   chmod +x time_execution.sh
   ```

### Lab Tasks

3. Execute all scripts and collect data:
   ```bash
   ./trace_commands.sh
   ./analyze_commands.sh > command_analysis.txt
   ./process_tree.sh > process_tree.txt
   ./time_execution.sh > timing_analysis.txt
   ```

4. Analyze strace outputs:
   - Compare fork() and exec() calls
   - Note differences in process creation
   - Identify system calls unique to each command type

5. Create a report documenting:
   - Command type characteristics
   - Process creation patterns
   - Performance differences
   - Shell behavior with different command types

### Deliverables
6. Command execution analysis report
7. Process trace logs
8. Performance comparison data
9. Documentation of findings regarding:
   - Built-in command execution
   - Alias expansion process
   - External command process creation
   - Shell process hierarchy

### Lab Questions

Answer the following questions based on your observations:

10. Why do built-in commands not show fork() calls in strace?
11. How does the shell handle alias expansion?
12. What's the performance difference between command types?
13. When would you use each type of command?
14. How does the process hierarchy differ for each command type?

### Extra Challenge

15. Create a custom command that:
   - Can be used as both built-in and external
   - Shows different behavior based on how it's called
   - Demonstrates the performance difference

16. Modify the analysis scripts to include:
   - Memory usage comparison
   - CPU utilization patterns
   - Process creation time analysis

### Notes
- Document all errors encountered
- Compare behavior across different shells (bash, zsh, etc.)
- Consider security implications of different command types

- - - 
## ***Sources:***