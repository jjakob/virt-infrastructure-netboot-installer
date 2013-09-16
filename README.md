virt-infrastructure-netboot-installer
=====================================

Quickly deploy KVM virtual machine hosts / clients with PXE &amp; preseeding


This set of customized Ubuntu 12.04 netboot installer files allows you to 
deploy virtual machine hosts and clients quickly using PXE netboot and preseeded definition files.

Currently the preseeded options include:

-en_SL locale (locale en, location Slovenia) and Slovenian keymap
-DHCP network config (can be customized manually after installation in interfaces file)
-SSH remote installation console

  For KVM hosts:
  -initial time config w/NTP 0.si.pool.ntp.org
  -LVM partitioning
  -packages ubuntu-standard, openssh-server, ubuntu-virt-server, ntp, linux-generic

  For virtual machines:
  -standard guided partitioning
  -packages ubuntu-standard, openssh-server, linux-virtual
  
  Also a standard Ubuntu netboot install menu is available.
  
  The installation requires an active DHCP server with the ability to configure for PXE booting,
  TFTP server (tftpd-hpa recommended) to serve the netboot-installer and HTTP server (apache etc) 
  to serve preseed files. (these can be run locally or in a virtual machine, but must be in 
  the same subnet with the target machines)
  
  Note: hostnames and specifics (minimally the locales, keymaps, TFTP, HTTP, proxy settings)
  for your setup will have to be configured manually in all appropriate places. A script to do this would be best, 
  but there is none at the moment. Not recommended for beginners.
