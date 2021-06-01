This repo is for review of requests for signing shim.  To create a request for review:

- clone this repo
- edit the template below
- add the shim.efi to be signed
- add build logs
- add any additional binaries/certificates/SHA256 hashes that may be needed
- commit all of that
- tag it with a tag of the form "myorg-shim-arch-YYYYMMDD"
- push that to github
- file an issue at https://github.com/rhboot/shim-review/issues with a link to your branch
- approval is ready when you have accepted tag

Note that we really only have experience with using GRUB2 on Linux, so asking
us to endorse anything else for signing is going to require some convincing on
your part.

Here's the template:

-------------------------------------------------------------------------------
What organization or people are asking to have this signed:
-------------------------------------------------------------------------------
SECURAZE GmbH based in Vienna, Austria

-------------------------------------------------------------------------------
What product or service is this for:
-------------------------------------------------------------------------------
SECURAZE Work & Command

-------------------------------------------------------------------------------
What's the justification that this really does need to be signed for the whole world to be able to boot it:
-------------------------------------------------------------------------------
SECURAZE offers SW solutions for secure data erasure on x86_64 and ARM based machines as well as smartphones - in order to properly sanitize data Securaze needs to be either locally or PXE booted on the machines to erase, as those typically come with Secureboot enabled as default it makes the process much easier for the end user.

-------------------------------------------------------------------------------
Who is the primary contact for security updates, etc.
-------------------------------------------------------------------------------
- Name: Markus Heiss
- Position: CEO
- Email address: markus.heiss@securaze.com
- PGP key, signed by the other security contacts, and preferably also with signatures that are reasonably well known in the Linux community:
-----BEGIN PGP PUBLIC KEY BLOCK-----

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
fD2M9UiBKGZSWQB+jYI7MA==
=OIbi
-----END PGP PUBLIC KEY BLOCK-----



-------------------------------------------------------------------------------
Who is the secondary contact for security updates, etc.
-------------------------------------------------------------------------------
- Name: Richie Feuersinger
- Position: CTO
- Email address: richie@securaze.com
- PGP key, signed by the other security contacts, and preferably also with signatures that are reasonably well known in the Linux community:
-----BEGIN PGP PUBLIC KEY BLOCK-----

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
+V9w/w==
=Vt2t
-----END PGP PUBLIC KEY BLOCK-----

-------------------------------------------------------------------------------
Please create your shim binaries starting with the 15.4 shim release tar file:
https://github.com/rhboot/shim/releases/download/15.4/shim-15.4.tar.bz2

This matches https://github.com/rhboot/shim/releases/tag/15.4 and contains
the appropriate gnu-efi source.
-------------------------------------------------------------------------------
We used the 15.4 repo with the latest critical patches

-------------------------------------------------------------------------------
URL for a repo that contains the exact code which was built to get this binary:
-------------------------------------------------------------------------------
https://github.com/richiesecuraze/shim/releases/tag/15.4.sec1

-------------------------------------------------------------------------------
What patches are being applied and why:
-------------------------------------------------------------------------------
No native patches, only those that are built in the rhboot Repo upon 15.4

-------------------------------------------------------------------------------
If bootloader, shim loading is, GRUB2: is CVE-2020-14372, CVE-2020-25632,
 CVE-2020-25647, CVE-2020-27749, CVE-2020-27779, CVE-2021-20225, CVE-2021-20233,
 CVE-2020-10713, CVE-2020-14308, CVE-2020-14309, CVE-2020-14310, CVE-2020-14311,
 CVE-2020-15705, and if you are shipping the shim_lock module CVE-2021-3418
-------------------------------------------------------------------------------
Yes


-------------------------------------------------------------------------------
What exact implementation of Secureboot in GRUB2 ( if this is your bootloader ) you have ?
* Upstream GRUB2 shim_lock verifier or * Downstream RHEL/Fedora/Debian/Canonical like implementation ?
-------------------------------------------------------------------------------
Downstream Debian implementation, in fact we are using the Debian GRUB2
GRUB2 2.04-17 from Debian sid
http://deb.debian.org/debian/pool/main/g/grub2/grub2_2.04-17.debian.tar.xz

-------------------------------------------------------------------------------
If bootloader, shim loading is, GRUB2, and previous shims were trusting affected
by CVE-2020-14372, CVE-2020-25632, CVE-2020-25647, CVE-2020-27749,
  CVE-2020-27779, CVE-2021-20225, CVE-2021-20233, CVE-2020-10713,
  CVE-2020-14308, CVE-2020-14309, CVE-2020-14310, CVE-2020-14311, CVE-2020-15705,
  and if you were shipping the shim_lock module CVE-2021-3418
  ( July 2020 grub2 CVE list + March 2021 grub2 CVE list )
  grub2:
* were old shims hashes provided to Microsoft for verification
  and to be added to future DBX update ?
* Does your new chain of trust disallow booting old, affected by CVE-2020-14372,
  CVE-2020-25632, CVE-2020-25647, CVE-2020-27749,
  CVE-2020-27779, CVE-2021-20225, CVE-2021-20233, CVE-2020-10713,
  CVE-2020-14308, CVE-2020-14309, CVE-2020-14310, CVE-2020-14311, CVE-2020-15705,
  and if you were shipping the shim_lock module CVE-2021-3418
  ( July 2020 grub2 CVE list + March 2021 grub2 CVE list )
  grub2 builds ?
-------------------------------------------------------------------------------
first submission, hence nothing shipped previously

-------------------------------------------------------------------------------
If your boot chain of trust includes linux kernel, is
"efi: Restrict efivar_ssdt_load when the kernel is locked down"
upstream commit 1957a85b0032a81e6482ca4aab883643b8dae06e applied ?
Is "ACPI: configfs: Disallow loading ACPI tables when locked down"
upstream commit 75b0cea7bf307f362057cc778efe89af4c615354 applied ?
-------------------------------------------------------------------------------
Yes, using Kernel 5.12.8

-------------------------------------------------------------------------------
If you use vendor_db functionality of providing multiple certificates and/or
hashes please briefly describe your certificate setup. If there are allow-listed hashes
please provide exact binaries for which hashes are created via file sharing service,
available in public with anonymous access for verification
-------------------------------------------------------------------------------
n/a

-------------------------------------------------------------------------------
If you are re-using a previously used (CA) certificate, you will need
to add the hashes of the previous GRUB2 binaries to vendor_dbx in shim
in order to prevent GRUB2 from being able to chainload those older GRUB2
binaries. If you are changing to a new (CA) certificate, this does not
apply. Please describe your strategy.
-------------------------------------------------------------------------------
n/a first submission

-------------------------------------------------------------------------------
What OS and toolchain must we use to reproduce this build?  Include where to find it, etc.  We're going to try to reproduce your build as close as possible to verify that it's really a build of the source tree you tell us it is, so these need to be fairly thorough. At the very least include the specific versions of gcc, binutils, and gnu-efi which were used, and where to find those binaries.
If possible, provide a Dockerfile that rebuilds the shim.
-------------------------------------------------------------------------------
Ubuntu 20.04 LTS - Dockerfile is provided at
https://github.com/securaze/shim-review/blob/master/docker/Dockerfile

-------------------------------------------------------------------------------
Which files in this repo are the logs for your build?   This should include logs for creating the buildroots, applying patches, doing the build, creating the archives, etc.
-------------------------------------------------------------------------------
full buildlog located here:
https://github.com/securaze/shim-review/blob/master/buildlog.txt

-------------------------------------------------------------------------------
Add any additional information you think we may need to validate this shim
-------------------------------------------------------------------------------
Thank you for your support ;-)
