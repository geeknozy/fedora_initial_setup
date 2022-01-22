# fedora_initial_setup
few things to do after fresh install of Fedora Linux distribution

-------------------------------------------------------------------------------------------------

## disable nouveau driver from grub 
```sudo nano /etc/default/grub```

Add ```nouveau.modeset=0``` to the end of line GRUB_CMDLINE_LINUX="rhgb quiet",
so that it should be : ```GRUB_CMDLINE_LINUX="rhgb quiet nouveau.modeset=0"``` after adding the config and save the file

Run : ```sudo grub2-mkconfig -o /boot/efi/EFI/fedora/grub.cfg``` (Fedora installation in EFI mode)
---------------------------------------------------------------------------------------------------
## Install chromium browser and remove the "fedora configuration" from browser (Managed by your Organisation menu will be removed)

1. Install the browser : ```sudo dnf install chromium```

2. Remove the fedora config : ```sudo dnf remove fedora-chromium-config```

## setup RPM Fusion Repository 
[rpm Fusion Wiki] (https://docs.fedoraproject.org/en-US/quick-docs/setup_rpmfusion/)

1. Enable Free rpm Fusion repository 
   Run : ```sudo dnf install \ https://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm```
   
2. Enable non-free Fusion repository
   Run : ```sudo dnf install \ https://download1.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm```
   
After the repository gets installed
Run : ```sudo dnf update``` 
while running this command the dnf asks for signature confirm, hit yes to confirm
