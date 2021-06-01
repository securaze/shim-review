Make sure you have provided the following information:

 - [ ] link to your code branch cloned from rhboot/shim-review in the form user/repo@tag
 - [X] completed README.md file with the necessary information
    https://github.com/securaze/shim-review/blob/master/README.md
 - [x] shim.efi to be signed
    https://github.com/securaze/shim-review/blob/master/shimx64.efi
 - [x] public portion of your certificate(s) embedded in shim (the file passed to VENDOR_CERT_FILE)
    https://github.com/securaze/shim-review/blob/master/certificate/codesign_ev_2021.cer
 - [ ] binaries, for which hashes are added do vendor_db ( if you use vendor_db and have hashes allow-listed )
 - [x] any extra patches to shim via your own git tree or as files
    https://github.com/richiesecuraze/shim/releases/tag/15.4.sec1
 - [ ] any extra patches to grub via your own git tree or as files
 - [X] build logs
    https://github.com/securaze/shim-review/blob/master/buildlog.txt



###### What organization or people are asking to have this signed:
SECURAZE GmbH based in Vienna, Austria

###### What product or service is this for:
SECURAZE Work & Command

###### Please create your shim binaries starting with the 15.4 shim release tar file:
###### https://github.com/rhboot/shim/releases/download/15.4/shim-15.4.tar.bz2
###### This matches https://github.com/rhboot/shim/releases/tag/15.4 and contains
###### the appropriate gnu-efi source.
###### Please confirm this as the origin your shim.
Yes, shim is compiled from exactly that source

###### What's the justification that this really does need to be signed for the whole world to be able to boot it:
SECURAZE offers SW solutions for secure data erasure on x86_64 and ARM based machines as well as smartphones - in order to properly sanitize data Securaze needs to be either locally or PXE booted on the machines to erase, as those typically come with Secureboot enabled as default it makes the process much easier for the end user.

###### How do you manage and protect the keys used in your SHIM?
Certificate is stored on a HW token in secure storage at the office with keyphrase only know to 3 members of the team

###### Do you use EV certificates as embedded certificates in the SHIM?
Yes

###### If you use new vendor_db functionality, are any hashes allow-listed, and if yes: for what binaries ?
Not used.

###### Is kernel upstream commit 75b0cea7bf307f362057cc778efe89af4c615354 present in your kernel, if you boot chain includes a Linux kernel ?
Yes, we are using Kernel 5.12.8 that has commit 75b0cea7bf307f362057cc778efe89af4c615354 embedded

###### if SHIM is loading GRUB2 bootloader, are CVEs CVE-2020-14372,
###### CVE-2020-25632, CVE-2020-25647, CVE-2020-27749, CVE-2020-27779,
###### CVE-2021-20225, CVE-2021-20233, CVE-2020-10713, CVE-2020-14308,
###### CVE-2020-14309, CVE-2020-14310, CVE-2020-14311, CVE-2020-15705,
###### ( July 2020 grub2 CVE list + March 2021 grub2 CVE list )
###### and if you are shipping the shim_lock module CVE-2021-3418
###### fixed ?
Yes, we are using Debian downstream GRUB2 

###### "Please specifically confirm that you add a vendor specific SBAT entry for SBAT header in each binary that supports SBAT metadata
###### ( grub2, fwupd, fwupdate, shim + all child shim binaries )" to shim review doc ?
###### Please provide exact SBAT entries for all SBAT binaries you are booting or planning to boot directly through shim
sbat 	1 	SBAT Version 	sbat 	1 	https://github.com/rhboot/shim/blob/main/SBAT.md
shim 	1 	UEFI shim 	shim 	1 	https://github.com/rhboot/shim
shim.securaze 	1 	Securaze 	shim 	15.4 	https://www.securaze.com/shim

##### Were your old SHIM hashes provided to Microsoft ?
No, this is our first submission.

##### Did you change your certificate strategy, so that affected by CVE-2020-14372, CVE-2020-25632, CVE-2020-25647, CVE-2020-27749,
##### CVE-2020-27779, CVE-2021-20225, CVE-2021-20233, CVE-2020-10713,
##### CVE-2020-14308, CVE-2020-14309, CVE-2020-14310, CVE-2020-14311, CVE-2020-15705 ( July 2020 grub2 CVE list + March 2021 grub2 CVE list )
##### grub2 bootloaders can not be verified ?
N/a

##### What exact implementation of Secureboot in grub2 ( if this is your bootloader ) you have ?
##### * Upstream grub2 shim_lock verifier or * Downstream RHEL/Fedora/Debian/Canonical like implementation ?
Downstream Debian like implementation.

###### What is the origin and full version number of your bootloader (GRUB or other)?
GRUB2 2.04-17 from Debian sid
http://deb.debian.org/debian/pool/main/g/grub2/grub2_2.04-17.debian.tar.xz

###### If your SHIM launches any other components, please provide further details on what is launched
Only GRUB2 is launched from SHIM

###### If your GRUB2 launches any other binaries that are not Linux kernel in SecureBoot mode,
###### please provide further details on what is launched and how it enforces Secureboot lockdown
N/A - only launching the Linux kernel.

###### If you are re-using a previously used (CA) certificate, you
###### will need to add the hashes of the previous GRUB2 binaries
###### exposed to the CVEs to vendor_dbx in shim in order to prevent
###### GRUB2 from being able to chainload those older GRUB2 binaries. If
###### you are changing to a new (CA) certificate, this does not
###### apply. Please describe your strategy.
N/A
###### How do the launched components prevent execution of unauthenticated code?
Stock Debian GRUB2 and Upstream Kernel with all relevant patches enabled

###### Does your SHIM load any loaders that support loading unsigned kernels (e.g. GRUB)?
No, only GRUB2 used.

###### What kernel are you using? Which patches does it includes to enforce Secure Boot?
Stock Linux Kernel 5.12.8 with all required Secure Boot patches

###### What changes were made since your SHIM was last signed?
N/A - first submission

###### What is the SHA256 hash of your final SHIM binary?
b3a877887a3965483aa9bcc267f5b9e1ae9eb25986ec99d57ca40efd5234ee48
