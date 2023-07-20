# Windows

## Commands
- __Get-Command__: help locate and display all available commands associated with specific requirement. When run with no option it returns all commands on sysem
  - Options:
    - "-Noun <\Argument>"
    - "-Name <\Argument>"
- __Get-Help__: Provide manual pages for commands (e.g. Get-Help Get-Process)
  - Without Options: provides Syntax, Examples, Descriptions, Related Links, Remarks, Name
  - Options:
    - "-Full": View the entire topic (i.e. Name, Synopsis, Syntax, Description, Parameters, Inputs, Outputs, Notes, Examples, Related Links)
    - "-Examples": get command Examples
    - "-Synopsis": get command Synopsis
    - "-Description": get command Description
    - "-Related Links": get command Related Links
    - "-Inputs": get command examples
    - "-Outputs": get command Outputs
    - "-Name": get command Name
    - 
- __Get-Member__: discover what objects, properties, and methods are avilable for a specific command
  - Options:
    - "-MemberType <\Argument>": Allow you describe the member type of the cmdlet gets
    - "-Name <\Argument>": Specifies the names of one or more properties or methods of the object
- __Get-WmiObject__: Return a WMI Object
  - Options:
    - "-Class <\Argument>
      - Arguments: 
        - win32_operatingsystem: Get windows operating system informaiton (e.g. Build Number, Version, Registered User, etc.)
        - win32_process: Get a list of running processes
        - win32_bios: Get bios (basic input and output system) information
- __Get-ExecutionPolicy__: Tells you the execution policy on the machine
  - Options:
    - "-List <\Argument>": view the current status of the machine's execution policy
    - "-Scope <\Argument>": define the granularity of view of the execution policy 
- __Set-ExecutionPolicy__: Sets the execution policy for the machine
  - Without any options you can pass the cmdlet the name of an execution policy (e.g. Set-ExecutionPolicy RemoteSigned)
- __Get-CimInstance__: Get the CIM (Common Information Model) instances of a class from a CIM server
  - Options:
    - "-ClassName <\Argument>":
        - win32_operatingsystem: Get windows operating system informaiton (e.g. Build Number, Version, Registered User, etc.)
        - win32_process: Get a list of running processes
        - win32_bios: Get bios (basic input and output system) information

## Pre-built Commands:
- LIST OS VERSION INFORMATION: Get-CimInstance -ClassName Win32_OperatingSystem | Select-Object -Property BuildNumber,BuildType,OSType,ServicePackMajorVersion,ServicePackMinorVersion
- LIST NUMBER OF LOCAL USERS AND OWNER INFO: Get-CimInstance -ClassName Win32_OperatingSystem | Select-Object -Property NumberOfLicensedUsers,NumberOfUsers,RegisteredUser
- DISPLAY SERVICE STATUS: Get-CimInstance -ClassName Win32_LogonSession
- SHUT DOWN DEVICE: Stop-Computer
- RESTART DEVICE: Restart-Computer
- LIST ALL FILES AND FOLDERS WITHIN A FOLDER: Get-ChildItem -Path C:\ -Force
- COPY FILES AND FOLDERS: Copy-Item -Path (path) -Destination (destination) - Force
- CREATE FOLDERS: New-Item -Path '(path)' -ItemType Directory
- CREATE FILES: New-Item -Path '(path)\(FileName.format)' -ItemType File

## Windows Nice To Knows
- Asterisk "*" can be used in PowerShell Script commands as wildcards (e.g. *service* : would return everything with the word service in it)
- If missing manual/help pages run "Update-Help" (may need to be run in administrator mode)
- Windows Objects represent an item are made of 3 types of data:
  - Object Type: Descriptions kind of object
  - Object Property: Information about the object
  - Object Methods: Actions that can be performed on the object
- Add "Read-Host -Prompt "Press Enter to exit" at the end of a PS script will stop the PS window for closing upon termination of process/program
- PS variables are prepended with a '$'

# Linux
- xfreerdp: Allows of the establishment of remote access to a Windows server
  - options for drive rediction (transferring files between client and server)

# MacOSX