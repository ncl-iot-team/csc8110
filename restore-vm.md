# Read this first before you continue
Only follow this if you accidentally deleted the VM. **You don't need to do this if you have the virtual machine!**

## 1. Recreate the virtual machine

1. Open the Hyper-V manager
2. On the right side of the maanger, create a new virtual machine
![image](https://user-images.githubusercontent.com/7325740/282494555-dc9d269a-d51b-48d1-81e7-41adfc31b886.png)
3. Provide the following information
  * Name: Cloud
  * Generation: 2
  * Memory: 8000MB
  * Networking: LabServicesSwitch
  * Virtual hard disk: Existing hard disk -> C:\Users\Public\Public documents\Hyper-V\Virtual hard disks\Cloud.vhdx

## 2. Configure the virtual machine
  * Right click the newly created VM and click settings
  * On the processor tab:
    * Give 4 virtual processors
  * On the security tab:
    * Make sure secure boot is turned **ON**
    * Change the security template to "Microsoft UEFI Certificate Authority"
    * Turn trusted platform moduule (TPM) and Shielding **OFF**
  * Click OK