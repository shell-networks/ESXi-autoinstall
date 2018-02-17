# ESXi-autoinstall
Auto install KS files (and other stuff) to autodeploy ESXi 6.5

Personnal project to automate deployment of Virtualisation part in my HomeLab  
In this repo is a short explanation of the hardware and network part of the lab.  
Then an How-to, to build your own custom ESXi ISO, to autodeploy the configuration.  

**1** - Home Lab Physical Servers  
**2** - Esxi Lab Virtual Servers  
**3** - Network Architecture  
**4** - How to use custom KS files to build an autodeploy ISO  
**5** - TODO List  


1. ## Home Lab Physical Servers

Here is a small overview (sorry for the cabling mess.. Hey this is home lab after all !)

![Home Lab picture](/Pictures/1-Home-Lab-Picture.jpg)

There is two Dell PowerEdge R610 Servers and a Cisco 3750G L3 switch.

Harware configuration for servers :

- Esx01 (on top)

2 Intel Xeon E5620  @2,4Ghz  
96GB of DDR3 RAM  
2 SAS Disks - 15k - 136Gb : RAID1 to host Esxi and Scratch log  
4 SAS Disks - 10k - 550Gb : RAID5 to host virtual machines  
4 integrated Gigabit Network interfaces (iSCSI compliant)  
4 Additional Gigabit Network interfaces  
iDRAC Management Port 

- Esx02 (obviously on bottom)

Same config as first one but only 48GB of RAM

2. ## Esxi "Lab" Virtual Servers

- Lab 01 and 02

They are just nested ESXi to test configuration before apllying on "prod" ESXi


3. ## Network Architecture

Because sometimes, a picture is better than a thousand of words...  
With this you will have a better understanding of the differents vlans that i configured in the Kickstart files.



4. ## How to use custom KS and build a personnalised ESXi autodeploy ISO

First of all, you need to download the ISO of Vmware ESXi 6.5  
https://my.vmware.com/web/vmware/details?downloadGroup=ESXI65U1&productId=614&rPId=21456

Then download a software to create bootable ISO.  
Personnaly i use ImgBurn, the installer is available in the Tools folder of this repository.

Once you have finished to download the ISO, copy the content of the ISO, in a new folder. Let's call this folder **Files_original**

Copy the content of the **Autodeploy** folder of this repo, at the root of the **Files_original** folder.  
You just copied the Kisckstart files and custom boot files... well, now lets create a new ISO !





All servers mentionned above have their configuration in a KS file.
There are two extra KS as well"features" :  
* A quick custom install
* VmWare standard install (nothing configured infact)







5. ## TODO - reminders for myself :)




