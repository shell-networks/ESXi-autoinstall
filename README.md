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
Personnaly i use ImgBurn, the installer is available in the Tools folder of this repository, or just follow the link.
http://www.imgburn.com/index.php?act=download

Once you have finished to download the ISO, copy the content of the ISO, in a new folder. Let's call this folder **Files_original**

Copy the entire content of the **Autodeploy** folder of this repo, at the root of the **Files_original** folder.  
You just copied the Kickstart files and custom boot files... well, now lets create a new ISO !

Launch ImgBurn and select **Create image file from files/folder**  
![2-ImgBurn](/Pictures/2-ImgBurn.jpg)  

Choose the folder **Files_original** as the source for the ISO creation, then for destination... wherever you want.
![3-ImgBurn](/Pictures/3-ImgBurn.jpg)  

In the advanced tab, tab bootable disc, hit the box "Make image bootable".  
Select the boot image **isolinux.bin**, at the root of your **Files_original** folder.  
Hit the box "patch boot information table".  
![4-ImgBurn](/Pictures/4-ImgBurn.jpg)

Finally you can build your ISO (you will be prompted for a name).

Now, lets boot on this ISO to see the result.  
As i have a Dell server, i will use the virtual media feature, from the iDRAC to mount the ISO on my server and boot on it.  
(Sorry for the french interface ahah)  
![5-iDRAC-VirtualMedia](/Pictures/5-iDRAC-VirtualMedia.jpg)

If you have this menu, then you just have to choose wich ESXi you wich ton install.  
![6-iDRAC-VirtualMedia](/Pictures/6-iDRAC-VirtualMedia.jpg)

All servers mentionned in differents points above have their configuration in a KS file.
There are two extra KS "features" as well:  
* A quick custom install
* VmWare standard install (nothing configured infact)







5. ## TODO - reminders for myself :)




