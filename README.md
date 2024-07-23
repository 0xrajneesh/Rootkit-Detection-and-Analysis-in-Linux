# Home-Lab: Rootkit Detection and Analysis in Linux

## Introduction

Rootkits are malicious software designed to hide the existence of certain processes or programs from normal methods of detection, allowing continued privileged access to a system. Detecting and analyzing rootkits is a crucial skill for cybersecurity professionals. This lab will guide you through intermediate-level techniques for detecting and analyzing rootkits on a Linux system.    

`Category`: Digital Forensics and Incident Response   
`Sub-Category`: Linux Forensics   
`Level`: Intermediate   

## Pre-requisites

- Intermediate understanding of Linux commands and file system structure.
- Basic knowledge of rootkits and their functionalities.
- A Linux system or virtual machine with sudo privileges.
- Familiarity with command-line interface (CLI).

## Lab Setup and Tools

### Lab Setup

1. Install a Linux distribution (e.g., Ubuntu, Fedora) on your system or set up a virtual machine using VirtualBox or VMware.
2. Ensure you have sudo access to install necessary tools and perform analysis.

### Tools

- `chkrootkit` - Rootkit detection tool
- `rkhunter` - Rootkit Hunter, a rootkit scanner
- `unhide` - Detect hidden processes and ports
- `strace` - System call tracer
- `lsmod` - Display loaded kernel modules
- `modinfo` - Show information about a kernel module
- `strings` - Find printable strings in files

## Exercises

### Exercise 1: Scanning for Rootkits with Chkrootkit

Objective: Learn how to use `chkrootkit` to scan for common rootkits and suspicious activities on a Linux system.

Step1: Install chkrootkit:
```bash
   sudo apt-get install chkrootkit
```
Expected Output: chkrootkit installed on the system.

Step2: Run chkrootkit scan

```bash
sudo chkrootkit
```
Expected Output: Scan results showing potential rootkits and suspicious files.

Step3: Analyze chkrootkit results:

```bash
less /var/log/chkrootkit.log
```
Expected Output: Detailed log of the scan results for further analysis.

### Exercise 2: Scanning for Rootkits with Rootkit Hunter (rkhunter)
Objective: Understand how to use rkhunter to detect rootkits, backdoors, and local exploits on a Linux system.

Step1: Install rkhunter:

```bash
sudo apt-get install rkhunter
```
Expected Output: rkhunter installed on the system.

Step2: Update rkhunter database:

```bash
sudo rkhunter --update
```
Expected Output: rkhunter database updated with the latest rootkit signatures.

Step3: Run rkhunter scan:

```bash
sudo rkhunter --check
```
Expected Output: Scan results showing potential rootkits and suspicious files.

Step4: Analyze rkhunter results:

```bash
less /var/log/rkhunter.log
```
Expected Output: Detailed log of the scan results for further analysis.

### Exercise 3: Detecting Hidden Processes and Ports with Unhide
Objective: Learn how to use unhide to detect hidden processes and network ports that may indicate the presence of a rootkit.

Step1: Install unhide

```bash
sudo apt-get install unhide
```
Expected Output: unhide installed on the system.

Step2: Detect hidden processes:

```bash
sudo unhide proc
```
Expected Output: List of hidden processes detected on the system.

Step3: Detect hidden network ports:

```bash
sudo unhide-tcp
```
Expected Output: List of hidden network ports detected on the system.

### Exercise 4: Analyzing Kernel Modules for Rootkits
Objective: Understand how to analyze loaded kernel modules to detect and investigate suspicious modules that may be part of a rootkit.

Step1: List loaded kernel modules:

```bash
lsmod
```
Expected Output: List of currently loaded kernel modules.

Step2: Get detailed information about a module:

```bash
modinfo <module_name>
```
Expected Output: Detailed information about the specified kernel module.

Step3: Check for suspicious modules:

```bash
lsmod | grep -i "rootkit"
```
Expected Output: Check if any loaded modules have names that might indicate they are rootkits.

### Exercise 5: Using Strace to Monitor System Calls
Objective: Learn how to use strace to trace system calls and signals, helping to detect abnormal behavior that might indicate rootkit activity.

Step1: Install strace:

```bash
sudo apt-get install strace
```
Expected Output: strace installed on the system.

Step2: Trace system calls of a running process:

```bash
sudo strace -p <pid>
```
Expected Output: Real-time display of system calls made by the specified process.

Step3: Analyze strace output:

```bash
sudo strace -o strace_output.txt -p <pid>
less strace_output.txt
```
Expected Output: Detailed trace of system calls written to a file for further analysis.

## Conclusion

By completing these exercises, you will gain an intermediate-level understanding of rootkit detection and analysis on Linux systems, enabling you to effectively identify and investigate rootkit infections.


## About Me

I am a cybersecurity trainer with a passion for teaching and helping others learn essential cybersecurity skills through practical, hands-on projects. Connect with me on social media for more updates and resources:

[![LinkedIn](https://img.icons8.com/fluent/48/000000/linkedin.png)](https://www.linkedin.com/in/rajneeshcyber)
[![YouTube](https://img.icons8.com/fluent/48/000000/youtube-play.png)](https://www.youtube.com/@rajneeshcyber)
[![Twitter](https://img.icons8.com/fluent/48/000000/twitter.png)](https://twitter.com/rajneeshcyber)

Feel free to reach out with any questions or feedback. Happy learning!
