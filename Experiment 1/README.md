# Experiment 1: Linux Installation Using Virtual Machine

## Aim
To install and configure a Linux operating system using a virtualization tool (Oracle VirtualBox or VMware Workstation) by importing an OVA file and preparing the system for Linux command-line and Bash scripting experiments.

## Objective
- Understand virtualization concepts
- Import and deploy a Linux OVA appliance
- Configure VM settings (RAM, CPU, Network)
- Verify Linux installation
- Prepare the environment for command-line and Bash scripting tasks

## Theory
Virtualization allows multiple operating systems to run on a single physical computer using virtual hardware. A Virtual Machine (VM) behaves like a real computer but runs inside software.

An OVA (Open Virtual Appliance) file is a preconfigured virtual machine package that contains an operating system, installed tools, and system configurations. Importing an OVA file simplifies deployment compared to manual OS installation.

Software Requirements:

1) Host System: Windows, macOS, or Linux.
2) Virtualization Software:
    -Oracle VirtualBox (free, recommended for beginners).
    -VMware Workstation.

3) Linux OVA File: A pre-configured Linux appliance (e.g., Ubuntu or Kali Linux; download from official sources or provided by your instructor).

Installation Procedure:
Using Oracle VirtualBox:

1) Install VirtualBox:
  -Download from the official website.
  -Install with default settings.
  -Launch VirtualBox Manager.

2) Import the OVA File:
  -Go to File > Import Appliance.
  -Select the .ova file.
  -Click Next, review settings, and click Import.
  -Wait for the process to complete.

3) Modify VM Settings:
  -Select the VM and click Settings.
  -System Tab:
     .Set RAM to at least 2048 MB.
     .Assign 2 CPU cores (if available).

  -Network Tab:
      .Set Adapter to NAT (recommended for basic networking).
 .Click OK.

4) Start the VM:
   -Click Start.
   -Wait for boot, then log in with provided credentials (e.g., username: root, password: as given).
   -Open the Terminal.


Using VMware Workstation:

1) Open VMware:
   -Launch VMware Workstation.
   -Click Open a Virtual Machine.
   -Select the .ova file and follow the import wizard.
   -Click Finish.

2) Configure VM Settings:
   -Select the VM and click Edit virtual machine settings.
   -Allocate:
        .RAM: Minimum 2 GB.
        .Processor: 2 cores.

   -Set Network to NAT.
   -Save settings.

3) Power On the VM:
   -Click Power on this virtual machine.
   -Log in with provided credentials.
   -Open the Terminal.


Verification
After logging in, open the Terminal and run these commands to confirm the setup:
  whoami    # Displays current user
  pwd       # Shows current directory
  ls        # Lists files in current directory
  uname -a  # Displays system information

Basic Configuration:
Once booted, update and install essential tools:
 # Update system
     sudo apt update
     sudo apt upgrade
  
 # Install essentials
    sudo apt install build-essential net-tools git curl

 # Verify Bash
    bash --version

Expected Outcome:
  -Linux successfully imported via OVA file.
  -VM configured with adequate resources (2 GB RAM, 2 CPU cores, NAT network).
  -Terminal accessible and functional.
  -System ready for Linux command-line and Bash scripting experiments.

Screenshots:
 For visual reference, see the attached images in the repo (extracted from the lab manual):
   -Cover page and problem statement.
   -VirtualBox import and settings.
   -VMware import process.
   -VM boot and terminal verification.

Result:
The Linux operating system was successfully installed and configured in a virtual environment using VirtualBox/VMware Workstation. The system is functional and ready for command-line operations and Bash scripting tasks.

Notes:
   -Ensure your host machine has sufficient resources (at least 4 GB free RAM, 2 CPU cores available).
   -For cyber security labs (e.g., using Kali Linux OVA), additional tools like Metasploit may already be pre-installed.
   -If issues arise during import, check OVA compatibility or increase host resources.
