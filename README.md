# BiosHater
WARNING! This is malware that can render your pc unbootable even to the UEFI level, proceed with caution!

# Info
The payload overwrites Sector 0 (LBA 0) with a custom MBR. Its basically a malformed Extended Partition entry.
The partition table contains an entry that points back to LBA 0 as its own container and when the motherboard powers on, the UEFI driver attempts to open the partition tree to identify bootable volumes but because the partition points to itself, the UEFI enters an infinite loop. On many devices, this happens before the UEFI initializes the keyboard or the display, resulting in a Black Screen that ignores UEFI keys to open it.

This exploit works even on virtual machines and with write protection on! But only works on UEFI devices, not old BIOS, still proceed with caution!  //my poor old laptop was tested with it and it resulted in a black screen while powering on :(

Language: C# .net framework 4.8 and assembly

Sources: https://mikeos.sourceforge.net/ (modified bootloader that is then overwriten to the MBR) and https://github.com/MalwareStudio/MBR_OVERWRITER_SOURCE_CODE for the C# MBR overwriter (By cyber soldier/clutter)

-zbezz :D
