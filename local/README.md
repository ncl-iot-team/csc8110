# Local virtual machine

We provide the following images for the coursework as an alternative to Azure lab. Both links requires you to login to your school account to download

Username: student

Password: CSC8110!

* For x86_64
  * [Download this image](https://newcastle-my.sharepoint.com/:u:/g/personal/nwhs3_newcastle_ac_uk1/EaJqrUewQExKv_qbtoo2KkUBPGwijmb3D-PRS-lD2bBXSA?e=QfXbU7)
  * Prerequisites:
    * Install [VMWare player / VMWare workstation](https://www.techspot.com/downloads/189-vmware-workstation-for-windows.html), [VMWare fusion](https://www.techspot.com/downloads/2755-vmware-fusion-mac.html) for Macs
      * Windows, Linux and Intel Macs
    * 30 GB+ storage
      * 8 GB RAM, 8 core CPU. Anything lower and you will get performance issues
* For arm64
  * [Download this image](https://newcastle-my.sharepoint.com/:u:/g/personal/nwhs3_newcastle_ac_uk1/EQMOKf_URLFGp9BLUUZNw4EBEuo6QwQlLE44ZH-HnkFKTA?e=pkqliq)
  * Prerequisites:
    * Install [UTM](https://getutm.app/)
    * ARM Macs only (e.g, M1, M2, etc.)
      * macOS Sequoia/macOS 15 and above
        * Configure the VM memory if your mac can afford it
        * 30+ GB stoage
          * If you have little disk space (<65GB), do not extract the .utm from the image. Just open the file directly
        * Rosetta
          * In a terminal, type `sudo softwareupdate --install-rosetta`

## Local VM troubleshooting

* [ARM Macs only] No Internet access / kubectl timeout in the VM
  * Power off, then edit the VM
  * At the network section, change the network mode to "Shared"
  * If that doens't work, switch it back to "Bridge" and try a different network interface
