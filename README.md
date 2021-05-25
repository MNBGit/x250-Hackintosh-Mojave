# x250-Hackintosh-Mojave
Necessary files to install Mac Os Mojave on a Thinkpad X250

## What works
touchpad
Trackpad
clickpad
Bluetooth
Ethernet


## What doesn't work
Wifi -> I need to buy a new wifi card compatible
Audio from jack (works fine with bluetooth)
Battery status

## Step 1
Create a Mojave bootable USB

## Step 2
Run Clover EFI bootloader download 
* Clover for UEFI booting only ☑️
* Install Clover in the ESP ☑️
* UEFI Drivers (assume you should de-select any listed driver not explicitly mentioned in this list)
  * Recommended drivers
  * De-select ⬛️ AudioDxe-64 (unless you really want to hear the Mac startup chime)
  * De-select ⬛️ DataHubDxe-64 (it's seemingly not needed on the X250)
  * Select ☑️ FSInject-64
  * De-select ⬛️ SMCHelper-64 (we're using VirtualSMC which comes with its own UEFI driver)
* File System drivers
  * Select ☑️ ApfsDriverLoader-64 (also available here, just in case it gets removed from the Clover installer)


## Step 3
Mount the EFI partition of the USB key (This is NOT an EFI folder with the USB Key. It is a separate partition that need to be mounted)
I use Clover Configurator.app for that (a small app like EFI mountain View works also. Or something like diskutil mount EFI but then I don't want it to get mixed up with real folders...)

## Step 4
Copy the entire EFI folder in EFI parition of the USB Key

## Step 4
Boot the USB an install mac OS

## Step 5.
Copy the same entire EFI folder from the git (or the USB) to the EFI partition OF THE DISK this time.

## Final Notes
Unibeast is an app that create the bootable mac OS USB + the necessary EFI files to boot. I don't remember if it works. If nothing works try that.
Multibeast is a post installation configuration EFI. I did not use that. It was much easier playing with files (like Kext) found after googling for specifically Thinkpad X250 directly in my EFI folder
