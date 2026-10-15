# CAPA: The Basics

### 1.Static vs Dynamic Analysis

    Static analysis: Examines a file without running it. This reduces the risk of executing potentially malicious code.

    Dynamic analysis: Runs a program in a controlled environment, such as a sandbox, to observe its actual behavior.

### 2.What is CAPA?

    CAPA (Common Analysis Platform for Artifacts) is a tool developed by the FireEye Mandiant team that uses predefined rules to identify capabilities in executable files and other supported artifacts.

    It can analyze formats such as:

    PE: Windows executable files, such as .exe and .dll.
    ELF: Commonly used for Linux executables.
    .NET modules: Components built using the .NET platform.
    Shellcode: Small pieces of code often used in exploitation.
    Sandbox reports: Reports containing observations from a program's execution.

### 3.What Can CAPA Identify?

    Network communication: Communicating with remote systems.
    File manipulation: Creating, reading, or modifying files.
    Process injection: Placing code into another running process.
    Persistence: Techniques that help software remain active on a system.

### 4.Why Is CAPA Useful

    Manually reverse engineering a program can be complex and time-consuming. CAPA automates part of this analysis by applying rules based on known software behaviors.

    Security analysts use it to investigate suspicious files, understand potential malware capabilities, and support threat hunting and incident response.

    Important: CAPA identifies capabilities based on patterns in a file. A finding does not automatically prove the file is malicious or that the behavior will actually occur.