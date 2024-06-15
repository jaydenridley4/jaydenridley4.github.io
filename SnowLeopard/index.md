# Mac OS X Snow Leopard (10.6.8) on a Mid 2011 MacBook Air
This page will be a tutorial on how to install Snow Leopard onto a Mid 2011 MacBook Air.\
This is easier than it looks... don't let the length decieve you - I just went into a great deal of detail for a novice.

## Prerequisites
* a Mid 2011 MacBook Air running OS X 10.7.5 (Lion)
* [VirtualBox 4.3](http://download.virtualbox.org/virtualbox/4.3.40/VirtualBox-4.3.40-110317-OSX.dmg)
* [Mac OS X Snow Leopard Install DVD](https://archive.org/details/mac-os-x-install-dvd)
* [Intel HD 3000 and additional kexts](/SnowLeopard/Kexts.zip)
* An internet connection

## Overview
**WARNING: I am not responsible for data loss in the unlikely event it occurs.**\
We are going to install Snow Leopard in a VirtualBox VM, update it as high as possible to fix some compatibility issues, then restore the VM HDD image to a seperate partition on your Mac.\
For this, you will need approximately 25 GB storage space for preperation. Later, we will delete some of that to make room for the Snow Leopard partition.

## Step 1 - Install VirtualBox
* Mount the VirtualBox 4.3 .dmg file from the prerequisites
* Open VirtualBox.pkg and follow instructions to install
    * Ignore any warnings about expired certificates, this is a legacy version
    * Default options will be fine for this tutorial

## Step 2 - Create the Snow Leopard VM
* Open VirtualBox, and select the "New" button in the top left corner
* Set the name to Snow Leopard, the type to Mac OS X, and the version to Mac OS X 10.6 Snow Leopard (64-bit). Press Next.
* Set the memory size to 1024 MB (higher is up to you). Press next.
* Select "Create a virtual hard drive now", and press next. Keep all options default, but change the size to 7 GB. Press Create.
* Select the Settings button in the top left corner, and go to the Storage tab. Click on the empty CD/DVD drive.
* Select the small CD/DVD icon towards the right, and select "Choose a virtual CD/DVD disk file". Find and open your Snow Leopard install ISO. Press OK to close the settings menu.

## Step 3 - Installing Snow Leopard
* Start the VM by selecting "Start" in the top left corner.
    * This may have verbose messages as the VM starts
    * The VM may take a while to start
* When you are at the language select screen, choose a language, press next, and select "Utilities" at the top of the window. Open Disk Utility.
* Select the hard drive, which will be called (capacity) VBOX HARDDISK.
* Go to the Erase tab, and choose a name for this virtual drive. I chose Snow Leopard.
* Leave other options default, and click Erase towards the bottom. Confirm erasing the disk.
* When it is done, press the red Close button to exit Disk Utility. Then, press Continue on the Install Mac OS X screen.
* Agree to the Terms and Conditions, and select your newly formatted disk. Press Customize.
* Select or deselect components you want or don't want.
    * The more you select, the more storage and time your image and install will take! Choose only what you need.
* Press OK to exit the menu, then press Install.
* **This will take a while to install. Wait until you are at the Setup Utility.**

## Step 4 - Setting up Snow Leopard and installing updates
* Go through the setup assistant, filling in any information you like. You can use your own if you want.
    * Do not use Migration Assistant
    * The Keyboard setup assistant may open. Complete that if it does.
* Once at the desktop, click the Apple menu, and select Software Update.
* Click "Show Details". Make sure **only** "Mac OS X Update Combined" is selected
    * We will do the rest once we have Snow Leopard on the Mac
* Click "Install 1 Item" at the bottom. Agree to the terms and conditions if prompted and enter your password.
    * **This will take some time**
* Once this update has completed and you are back at the desktop, shut down your virtual machine.

## Step 5 - Imaging your Snow Leopard virtual machine
* On the VirtualBox main menu, open the Settings menu, and go to the Storage tab. Click the SATA controller and press the blue button at the bottom to add a new hard disk.
* Choose "Create a new disk". **Set the format to VMDK**. Make the size bigger than your Snow Leopard disk. I used 14 GB for my image drive.
* Start the Virtual Machine. **Press Fn+F12 as soon as the VM starts - you must click into the VM first.**
    * This **will** take many attempts - also, if it asks if you want to be prompted every time, press no.
    * You will be at a screen with "Boot Maintenance Manager" at the bottom.
* Use the arrow keys to select "Boot Manager". Press Return.
* Use the arrow keys to select the second "Mac Boot". Press Return.
    * If this boots to the desktop, try the other one.
    * The one we want mentions CDROM on the right hand side somewhere.
* Choose a language, then open Disk Utility from the Utilities menu.
* Select the bigger drive with no volumes, go to the Erase tab, and choose a name. I chose "Image". Press Erase and confirm.
* When done, click the smaller disk in the left menu.
    * Click the VBOX HARDDISK listing instead of your Snow Leopard one.
* Select "New Image" at the top menu. In the "Where" menu, set it to your newly formatted drive.
* Leave all other options default. Click "Save" and wait until it completes.
* When it is complete, click the Apple menu and restart the virtual machine.
    * If you cannot select that, close Disk Utility then quit the Mac OS X Installer from the menu bar
    * This time, you want it to be on the desktop after it reboots - no need to hit Fn+F12.

## Step 5.5 - Copying the image to Mac OS X Lion
**This section is definitely not the best way to do it, so please let me know if you found a better way.**
* You should be back at the desktop. You might get a prompt for Time Machine, if so, click Don't Use
* **On your Mac OS X Lion host** open System Preferences, and go to the Sharing page. Turn on File Sharing.
* **On your Mac OS X Snow Leopard guest** go to the Go menu at the menu bar, select Network. Locate your Lion host.
* Double click your Lion host, then press Connect As. Select Guest, and press OK.
    * You can use your account details, but for this example we will use Guest.
* Open your account's Public Folder.
* In another window, find your image we created in Step 5. It should be in a drive on the desktop.
* Drag and drop that image into your Drop Box in your Public Folder in the other window.
    * Depending on the size of your image, this may take some time.
* When done, shut down your Virtual Machine. We will not be needing it anymore.
    * If you want, you can delete it from the VirtualBox main menu by right clicking, and pressing Delete.
    * Feel free to turn off file sharing on your Mac OS X Lion host in System Preferences -> Sharing, if you like.

## Step 6 - Creating your Snow Leopard partition and restoring your image
* Find the image you copied in the Drop Box in the public folder of your Lion host. Mount it by double clicking it.
    * This will be at /Users/(your username)/Public/Drop Box/
    * To save time, you can select Skip when it is verifying.
    * You can close Finder after doing this
* Open Disk Utility from the Utilities folder in Launchpad
* Select your Mac's internal SSD, and go to the Partition tab
* Select the plus icon to add another partition. Adjust the sizing as to you would like.
    * The size must be larger than 13 GB (what we set the virtual image's size to be in Step 2)
    * I went with 30 GB.
    * Don't worry about changing the name, you need to do that after we restore the image
* Click Apply to save your changes. Then click Partition.
    * Once this is complete, you will see another partition under your Lion partition on the left
* Click your new partition on the left bar. Go to the Restore tab.
* Drag and drop your new partition (the one we just erased) into the Destination field
* Drag and drop your mounted Snow Leopard partition to the Source field
* Select Restore, select Erase and type your password.
    * This will take some time.
* Unmount the Snow Leopard image at the bottom of Disk Utility's left pane

## Step 6.5 - Installing required kexts
* Download and extract the kexts provided in the prerequisites
* Delete these kexts from your Snow Leopard's /System/Library/Extensions folder
    * AppleIntelHDGraphics.kext
    * AppleIntelSNBGraphicsFB.kext
    * IOPlatformPluginFamily.kext
* Copy the same kexts from the zip file to your new Snow Leopard partition's Extensions folder

## Step 7 - Booting Snow Leopard
* Now for the fun part - booting Snow Leopard!
* Shut down your Mac
* Turn your mac back on, but hold the Option key until you reach the boot picker.
* Use the arrow keys or the trackpad to select your Snow Leopard partition
* Press the Enter key to boot Snow Leopard.
    * This may take longer than Lion due to certain missing kexts

## Post Install
### Connecting to the Internet
* To connect to Wi-Fi, open System Preferences, go to the Network page, and find your Wi-Fi network from there.
### Updating software
* Open Apple Software update from the Apple menu, and install updates how we did in Step 4.

## Images

![Mac OS X Snow Leopard "About This Mac" page on a Mid 2011 MacBook Air](/SnowLeopard/AboutThisMac.png "Mac OS X Snow Leopard About This Mac page on a Mid 2011 MacBook Air")