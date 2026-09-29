**Windows Digital Forensics — Disk & Memory Images**

    When investigating a Windows computer, forensic investigators usually create forensic images before analyzing the system.

    A forensic image is a bit-by-bit copy of digital data that can be analyzed without working directly on the original evidence.

    There are two important types:

    1. Disk Image

    A disk image is a copy of the data stored on the computer's HDD/SSD.

    This data is non-volatile, meaning it remains after the computer is shut down.

    It can contain:

    Documents
    Photos/videos
    Installed programs
    Browser history
    Deleted files
    File metadata
    Operating system files

    HDD / SSD
        ↓
    Bit-by-bit copy
        ↓
    Disk Image
        ↓
    Forensic Analysis

    Example: An investigator can examine a disk image to determine whether a suspicious file was downloaded or whether files were deleted.


    2. Memory Image

    A memory image is a copy of the computer's RAM at a specific moment.

    RAM is volatile, meaning its contents disappear when the computer is powered off or restarted.

    It can contain things such as:

    Running processes
    Open files
    Network connections
    Loaded programs
    Potential malware
    Other temporary information

    Therefore:

    If the computer is still running, memory acquisition is often prioritized before shutting it down.

    Otherwise, volatile evidence may be lost.

**Common Forensics Tools**

    FTK Imager

    FTK Imager is commonly used to:

    Acquire disk images
    Preview/examine evidence
    Work with different forensic image formats

    FTK Imager → acquire and inspect disk evidence


    Autopsy

    Autopsy is an open-source digital forensics platform used primarily for analyzing disk images.

    It can help find:

    Deleted files
    Keywords
    File metadata
    Browser artifacts
    Suspicious files
    Extension mismatches

    Autopsy → investigate what's inside a disk image


    DumpIt

    DumpIt is used to acquire a memory image from a Windows system.

    DumpIt → capture RAM


    Volatility
    Volatility is an open-source framework used to analyze memory images.

    It can examine artifacts such as:

    Processes
    Network connections
    Loaded modules
    Malware-related artifacts

    It supports multiple operating systems, including Windows and Linux.

    Volatility → investigate what's inside a memory image


**Key Takeaway**

    Disk image = persistent data from storage.
    Memory image = temporary data from RAM.

    Forensics tools then allow investigators to acquire and analyze these images without directly working on the original evidence.