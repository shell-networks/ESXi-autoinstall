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

- Esx01

2 Intel Xeon E5620  @2,4Ghz

96GB of DDR3 RAM

2 SAS Disks - 15k - 136Gb : RAID1 to host Esxi and Scratch log

4 SAS Disks - 10k - 550Gb : RAID5 to host virtual machines

4 integrated Gigabit Network interfaces (iSCSI compliant)

4 Additional Gigabit Network interfaces

- Esx02

Same config as first one but only 48GB of RAM


2. ## Esxi "Lab" Virtual Servers

- Lab 01 and 02

They are just nested ESXi to test configuration before apllying on "prod" ESXi


3. ## 2 Network Architecture

Because sometimes, a picture is better than a thousand of words...


4. ## How to use custom KS to build an autodeploy ISO

5. ## TODO - reminders for myself :)




