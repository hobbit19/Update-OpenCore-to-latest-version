# Update OpenCore to the latest version
Update OpenCore (and EFI) to latest version using OpenCore Configurator

![alt test](/Pictures/OpenCoreUpdate.png)

# Introduction
Many of you asking how do I upgrade my OpenCore to the latest version. Updating OpenCore is not so easy as i.e. updating Clover, so therefore I made myself a small how-to to make lives easier. Hopefully this is of value to you.

Steps I undertake to upgrade OpenCore to the latest (stable) released build (it now takes me 30 minutes to do this per system): 

# Check the Dortania website
This is important for you to understand the changes in OpenCore. Dortania made a small how-to:
https://dortania.github.io/OpenCore-Post-Install/universal/update.html
And the Differences comparison can be handy:
https://github.com/acidanthera/OpenCorePkg/blob/master/Docs/Differences/Differences.pdf

The thing I find not so usefull here, is that you need to understand everything in the document, which is not so good for the more beginning hackintoshers (like myself). So, therefore, I follow my own little procedure as per below. 


# OC Gen-X
With OC Gen-X I generate my config.plist (and nothing more than that…) so that it’s based on OpenCore latest release build. 

Step 1:
Install OC Gen-X.app. Download from: https://github.com/Pavo-IM/OC-Gen-X 

Step 2:
Explanation per tab:

Step 2a:
System Type
-	Choose System (processor) type and don’t select any kexts or drivers. (E.g. i7 9700, choose Coffee Lake).

Step 2b:
Kext
-	don’t select anything

Step 2c:
Firmware Drivers
-	don’t select anything

Step 2d: 
SMBIOS
-	Fill SMBIOS with your current serials etc. Use OpenCore Configurator to get the info from your current config.plist

Step 2e:
Additional BootArgs
-	Fill in your current used boot arguments

Step 2f:
Click Generate EFI and use only the generated config.plist from the generated folder.


# OCBuilder
With OCBuilder I create my core EFI folder so that it’s based on OpenCore’s latest release build. 

Install OCBuilder.app. Download from: https://github.com/Pavo-IM/ocbuilder 

-	Select version: ‘Release’, with Kexts (it downloads the latest kexts from the appropriate Github page).
-	Choose a location to save the EFI folder (e.g. desktop) and click ‘Build’.

# How to proceed? 
-	Open the EFI folder you just created and copy the created config.plist in there
-	Copy all of your DDST’s, ACPI’s and drivers from your current (old) EFI to the folders you just created, and make sure you will use the latest kexts (you just downloaded most of them)

# OpenCore Configurator
-	Download the latest here: https://mackie100projects.altervista.org/download-opencore-configurator/ 
-	Open your newly made config.plist with OpenCore Configurator and load all your DDST’s, ACPI’s, Drivers and Kexts.
-	Now, compare with 2 OpenCore Configurator screens your current (old) config.plist with your newly made config.plist, to make sure all your settings are also in the new one.

That’s it. Of course, before you load your new EFI, make sure you have a back-up which you can load back if things failed. 
