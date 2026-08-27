**What is PowerShell?**
    - is a cross-platform command-line shell and scripting language developed by Microsoft for system administration, task automation, and configuration management on Windows, Linux, and macOS.

**Basic PowerShell Syntax: Verb-Noun**
    - Verb describes the action
    - Noun describes the object the action is performed on
    - Example:
        1. Get-Content - displays the contents of a file.
            - Get → retrieve something
            - Content → the content of a file
        2. Set-Location - changes your current working directory.
            - Set → change or configure something
            - Location → the current directory

**Basic Cmdlet**: 
1. Get-Command
    - To see the commands available in your current PowerShell session.
    - This can list available:
        1. Cmdlets
        2. Functions
        3. Aliases
        4. Scripts
    - Examples:
        - Get-Process   → Get information about processes
        - Get-Service   → Get information about services
        - Stop-Process  → Stop a process
        - Set-Location  → Change the current location/directory
2. Get-Help
    - provides detailed information about cmdlets, including usage, parameters, and examples
    - Eg. Get-Help Get-Date "%A %B/%d/%Y"
3. Get-Alias
    - shortcuts or alternative names for cmdlets
    - For example, dir is an alias for Get-ChildItem, and cd is an alias for Set-Location
    
**Standard PowerShell Syntax**
    - Cmdlet -Property "pattern*"

**Find and Download Additional Cmdlets:**
    - Feature of PowerShell extending its functionality
    - Find-Module cmdlet
        - for finding online repos. eg. Find-Module -Name "PowerShell*" 
    - Install-Module
        - download and install from a repository. eg. Install-Module -Name "PowerShellGet"

**Navigating the File System and Working with the Files**
1. Get-ChildItem
    - lists the files and directories in a location specified with the -Path parameter.
2. Set-Location
    - Navigate to different directory.
3. New-Item
    - create an item. It requires to specify the path of the item and its type (file or a directory)
    - eg. New-Item -Path "./myfolder1/myfolder2" -ItemType "Directory"
    - eg. New-Item -Path "./myfolder1/myfolder2/example.txt" -ItemType "File"
4. Remove-Item
    - removes both directories and files
    - Remove-Item -Path "./myfolder1/myfolder2/example.txt"
    - Remove-Item -Path "./myfolder1/myfolder2"
5. Copy-Item and Move-Item  
    - copy or move files and directories
    - Copy-Item -Path ./newfolder/test.txt -Destination ./test2.txt 
    - Move-Item -Path ./test2.txt -Destination ./newfolder/
6. Get-Content
    -  to read and display the contents of a file

**Piping, Filtering, and Sorting Data**
1. Piping
    - is a technique that sends the output of one command directly as input to another command.
    - sequence of operations where data flows from one to next command
    - represented by pipe "|" symbol
    - eg. Get-ChildItem | Sort-Object Length - get a list of files in a directory and then sort them by size
Filter objects based on specified conditions:
    - eg. Get-ChildItem | Where-Object -Property "Extension" -eq ".txt"
Other examples:
    - Get-ChildItem | Where-Object -Property "Name" -like "ship*" - Filters the object with a "ship" name
    - Get-ChildItem | Select-Object Name,Length - Select specific properties from an object or limit the number of objects returned.
    - Get-ChildItem | Sort-Object Length -Descending | Select-Object -First 1 - Sort and Filter displaying the Largest file
    - Select-String
        - searches for text patterns within files, similar to "grep"
        - eg. Select-String -Path ".\captain-hat.txt" -Pattern "hat" 

**System and Network Information**
1. Get-ComputerInfo
    - retrieves comprehensive system information, including operating system information, hardware specifications, BIOS details, and more.
2. Get-LocalUser
    - lists all the local user accounts on the system.
3. Get-NetIPConfiguration   
    -  provides detailed information about the network interfaces on the system, including IP addresses, DNS servers, and gateway configurations. similar to ipconfig

**Real-time Analysis**
1. Get-Process
    - display detailed current running processes, including CPU and memory usage
2. Get-Service
    - retrieval of information about the status of a service on the machine
3. Get-NetTCPConnection
    - displays current TCP connections
4. Get-FileHash
    - generating file hashes
    - valuable in incident response, threat hunting, and malware analysis, as it helps verify file integrity and detect potential tampering.

**Scripting**
    - Scripting is a series of command executed automatically in a file. It overcomes manual execution or typing each command.
    - Invoke-Command
        - is a PowerShell cmdlet used to run commands or scripts, either on a local computer or on a remote computer.   
**Why Does Scripting Matter in Cybersecurity?**
Cybersecurity often involves repetitive tasks, such as:
    - Checking hundreds of log files
    - Collecting system information
    - Searching for suspicious IP addresses
    - Checking running processes
    - Automating incident-response tasks

 


        
        