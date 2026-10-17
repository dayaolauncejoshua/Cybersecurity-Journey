# FlareVM - Commonly Used Tools

    These tools are commonly used during initial malware investigations. Each helps an analyst examine a different part of a suspicious file or system.

### 1.Procmon (Process Monitor)

    Records real-time file system, Registry, process, and thread activity.

    Example: Detects a suspicious program creating files or modifying Registry entries.

### 2.Process Explorer

    Examines running processes, parent-child relationships, loaded DLLs, and executable paths.

    Examples: Identifies a suspicious process launched by Microsoft Word.

### 3.HxD

    Hex editor for viewing and editing raw file bytes. 

    Example: Inspect a file header to check whether the file type matches its extension.

### 4.Wirehark

    Captures and analyzes network packets.

    Example: Investigates whether a suspicious program communicates with an unknown IP address.

### 5.CFF Explorer

    Inspects and edits Windows Portable Executable (PE) file structures; can also calculate hashes.

    Example: Examines an executable's headers, sections, and imported functions.

### 6.PEStudio

    Performs static analysis of executable files without running them.

    Example: Identifies suspicious imports, strings, indicators, and executable properties.

### 7.FLOSS

    Extracts and decodes strings that malware may hide or obfuscate.

    Example: Reveals in hidden URLs, commands, or other text that ordinary string extraction may miss.