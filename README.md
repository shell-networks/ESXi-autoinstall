# ESXi-autoinstall
Auto install KS files (and other stuff) to autodeploy ESXi 6.5

Personnal project to automate deployment of Virtualisation part in my HomeLab

## 1 Home Lab Physical Servers

There is two Dell PowerEdge R610 Servers with following Hardware configuration 

1. Esx01

2 Intel Xeon E5620  @2,4Ghz
96GB of DDR3 RAM
2 SAS Disks - 15k - 136Gb : RAID1 to host Esxi and Scratch log
4 SAS Disks - 10k - 550Gb : RAID5 to host virtual machines
4 integrated Gigabit Network interfaces (iSCSI compliant)
4 Additional Gigabit Network interfaces

2. Esx02

Same config as first one but only 48GB of RAM


## Esxi "Lab" Virtual Servers

- Lab 01 and 02

They are just nested ESXi to test configuration before apllying on "prod" ESXi


## 2 Network Architecture

## 3 How to implement Autodeploy with custom KickStart files




