# CSC8110 Cloud Computing – Assessment 1

This repository contains essential materials and references for the practicals of CSC8110 Cloud Computing module.

## Table of Contents

* [Getting started (Azure lab)](#getting-started-azure-lab)
	* [Azure lab troubleshooting](#azure-lab-troubleshooting)
* [Getting started (Local virtual machine)](#getting-started-local-vm)

## Getting started (Azure lab)

1. Access Azure lab
    * Go to [Azure lab](https://labs.azure.com/), login with your student account
        * Use this (c12345678@newcastle.ac.uk) email, not this (a.a.name1@newcastle.ac.uk) email
    * Click the icon next to the VM power button

2. Setup remote connection
    * Download the .rdp file by clicking the blue computer icon
    * Login for the VM (Both Windows and Ubuntu)
        * Username: student
        * Password: CSC8110!
    * For Windows
        * Directly run the file with remote desktop connection
    * For Mac
        * Download [Microsft Remote Desktop](https://apps.apple.com/us/app/microsoft-remote-desktop/id1295203466?mt=12) from the App Store
    * For Linux
        * Install any RDP client from your package manager

3. Access the Ubuntu VM
	* Once you logged into the Windows desktop, open the Hyper-V Manager
	* Click these two buttons to start and connect to the VM
		* ![](hyper-v-startvm.png)

### Azure lab troubleshooting

* No Internet connection
	* Power off the Ubuntu VM, then power off the Azure lab. Wait for 15 minutes. Power on and try again
* Accidentally deleted the Ubuntu VM
	* Refer to [this link](restore-vm.md)

## Getting started (Local VM)

We provide the following images for the coursework as an alternative to Azure lab. Both links requires you to login to your school account to download

* For x86_64
    * [Download this image](https://newcastle-my.sharepoint.com/:u:/r/personal/nwhs3_newcastle_ac_uk1/Documents/VM%20Images/CSC8110-KDocker_amd64.ova?csf=1&web=1&e=5zje4m)
    * Requires [VMWare player](https://www.vmware.com/uk/products/workstation-player.html) to run
* For arm64 (Mac M1/M2/etc.)
    * [Download this image](https://newcastle-my.sharepoint.com/:u:/g/personal/nyl44_newcastle_ac_uk/EWhxOiJnYAxAsB5Ze_xIP04BD8PdEu_HV4V7EQmpH36YtQ?e=vKwSuK)
    * Requires [VMWare fusion](https://www.vmware.com/uk/products/fusion.html) to run
    

