# Haiku OS

Haiku
-----

Link: https://drive.google.com/open?id=1FW43GtIjVe4c2KLfCnWbx2CCKKMkGkhI

Extract `haiku.7z` and run in QEMU with: `qemu-system-x86_64 -M accel=kvm:tcg -soundhw hda -m 512 -hda haiku-r1alpha4.vmdk -hdb "blank-bfs-2048mb.vmdk"`

Information about Haiku from their website https://www.haiku-os.org/about :

HAIKU is an open source operating system currently in development.
Specifically targeting personal computing, Haiku is a fast, efficient, simple
to use, easy to learn, and yet very powerful system for computer users of all
levels. Additionally, Haiku offers something over other open source platforms
which is quite unique: The project consists of a single team writing everything
from the kernel, drivers, userland services, tool kit, and graphics stack to
the included desktop applications and preflets. While numerous open source
projects are utilized in Haiku, they are integrated seamlessly. This allows
Haiku to achieve a level of consistency that provides many conveniences, and
is truly enjoyable to use by both end-users and developers alike.

= HAIKU R1 Alpha 4.1 Release Notes =

These are the release notes for HAIKU R1 Alpha 4.1, a critical bugfix update for our fourth official release. For this fourth alpha release, we strove to provide an improved version of Haiku that is more stable, introduces more features for both the end-user and developer, and has a greater chance of properly booting on more hardware.  

We have tried hard to make this release as good as possible. Still there are a few known issues and missing features, some of them collected below. Please keep in mind that this is alpha software, which means it is not yet feature complete and still contains known and unknown bugs. While we are mostly confident in the stability of this release, we do not provide any assurances against data loss.

Another goal that has driven the release of the Alpha 4 was to provide current and future Haiku developers an updated and (mostly) stable operating system to work on their software projects. Therefore we have included the basic build tools. This release of Haiku is capable of building and running binaries using either GCC 2 or GCC 4. The use of GCC 4 is discouraged however if not absolutely necessary, as no API compatibility is guaranteed with future versions of Haiku.

Due to the immediate testing efforts of Release 1 Alpha 4, we are able to release this critical bugfix version. The specific bugs fixed in this point release are http://dev.haiku-os.org/ticket/8684, http://dev.haiku-os.org/ticket/9128, and http://dev.haiku-os.org/ticket/9148. These issues prevented Haiku from booting properly on several hardware configurations.

Thank you all who reported the issues on the bug tracker and we appreciate your understanding.

== System Requirements ==

Haiku currently only works on x86 systems. Minimum memory required is 128 MB. If compiling Haiku within itself, 1 GB of memory is recommended. Haiku has been tested to work on CPUs as slow as a Pentium II 400 MHz, and requires as little as 700 MB of drive space.

== New Features ==

This is a glimpse into some of the more notable improvements and additions to Haiku, since the previous release, R1 Alpha 3. It should be noted that over 1000 bugs closed as fixed since R1 Alpha 3. Additionally, more than 100 subtle bugs have been fixed, which were discovered by Coverity.

Wireless networking now supports WPA/WPA2. (See "Workshop: Wireless networking" in the HAIKU User Guide)

Various enhancements for hardware support, such as video drivers (radeon hd, intel extreme), network drivers, OHCI USB, PS/2, initial Blu-ray Disc (UDF 2.50), Sandy Bridge CPUs, and better AMD/Intel CPU name detection

Added pcnet network driver, which eases the use of VirtualBox to run Haiku

Additional applications include a native debugger application (Debugger), a utility for assisting users of multiple keymaps (KeymapSwitcher), a 10 channel equalizer media add-on, and a new GLife screensaver donated by Aaron Hill

Updated WebKit, which improves rendering in the native browser WebPositive

StackAndTile, a method for managing multiple windows, has been improved (OPT + first mouse button to activate stacking and tiling of adjacent windows)

IPv6 modules added

The BFS file system is more robust and has new tools for detecting and correcting issues

Support for very large disks and partitions (greater than 63 TB)

Improved virtual memory settings and swap file creation logic

Additional KDL debugging tools, including the ability to generate QR codes from the debug output

Numerous potential memory leaks fixed

Expanded the POSIX signal support with real-time extensions

Update of the secondary and experimental compiler to GCC 4.6.3 (available via setgcc gcc4)

Update of OpenGL kit to newer Mesa3D 7.8.2 

== Missing Features ==

Package management is still being developed and is not included in this release. For the time being, a temporary script is included to help install a small set software (available via `installoptionalpackage`).

== Known Issues ==

LiveCD and first boot performance: After an initial installation or a boot into LiveCD mode, some background tasks are executed to finish the installation setup. This is known to degrade performance. On hard disk installs this usually is not a problem as the tasks are done quickly. In LiveCD mode the performance hit is more prominently visible due to the usually bad seek performance on CDs. Since the CD is read-only, this setup takes place on every start of the LiveCD. On writable media it will only be done once, so further boots shouldn't experience the same delays.

Font rendering, while improved due to the expired font hinting patent, is still not optimal. Due to the uncertain situation about patents, the official release has disabled code, which is known to be patented. This sadly includes the subpixel code used by FreeType. Once the situation is better understood and a decision has been made, subpixel font rendering may get re-enabled for official releases.

Haiku's ACPI support, which is enabled by default, might cause problems on some hardware. ACPI can be disabled in the boot loader's safe mode options menu.

Copying large amounts of data from faster to slower disk drives (like USB sticks) can cause the system to start paging.

The Haiku boot loader has been reported to hang on some hardware.

Support for localization/internationalization is still a work in progress. Some applications might only be partially translated and have issues with long strings in languages other than English.

Firmware for some wireless network cards need user acknowledgement, prior to their installation. This includes Broadcom 43xx, Intel ipw2100, Intel ipw2200 and Marvell 88W8335. As a temporary measure, a script is included to assist in this process (available via `install-wifi-firmwares.sh`).

Some Marvell Yukon cards are known to have low network performance. 

The IMAP protocol for the mail daemon replacement (MDR) has been removed from this release, due to concerns of losing server side data.

Due to size constraints of CDs, several developer related tools have been removed (e.g., hg, svn, cvs, python. They can be installed via `installoptionalpackage`)

== Source Code ==

The source code of Haiku itself, the source code of the required build tools and the optional packages (except for closed source ones) is made available for download at: http://www.haiku-files.org/files/releases/r1alpha4/sources/

== Reporting Issues ==

There are over 2400 open tickets on Haiku's bug tracker and over 6600 closed items.  If you find what you believe to be an issue, please search our Trac to see if it has already been reported, and if not, file a new ticket: http://dev.haiku-os.org/

To see the list of tickets reported in Haiku R1 Alpha 4, visit http://dev.haiku-os.org/wiki/R1/Alpha4/ReportedIssues

For information about major issues that have been fixed since the release, visit http://dev.haiku-os.org/wiki/R1/Alpha4/ReleaseAddendum

For more help see the 'Welcome' link on the Haiku desktop, or visit the Haiku Project's website at www.haiku-os.org.
