# Basics
- Scripting lanaguage native to Windows that can be installed on MacOS and Linux
- Language is used for the automation of administrative tasks
  - Manage Active Directory
  - Track Key Monitoring Metrics
  - Automation of Mangement Tasks
- There is vast difference in the capabilities of powershell when in elevated (Administrative) versus normal
  - With elevated privileges a user can do damage/harm to the system
  - When in Elevated mode the title of the application reads "Administrator - Windows PowerShell"
- cmdlets are PowerShell commands that can be used in the PS (PowerShell) environment
  - In Form: Verb-Noun - verb specifies the action taken by the cmdlet, noun specifies the resource the cmdlet acts upon
    - cmdlet("verbName", "nounName)
    - Cmdlet with Options: cmdlet("verbName", "nounName, Name Parameters)

## Execution Policy
- By default the execution policy is set to restricted
  - Exists to prevent the accidental running of a PS script that could damage the System

## Restricted
- Enabling this option does not allow any PS scripts to run

## Unrestricted
- When this option is set, users can run any script, however, Windows, shows a warning when trying to run downloaded scripts

## RemoteSigned
- When this option is set, downloaded scripts require a digital signature, however, you can run locally written scripts, and although it's not recommended you can even unblock downloaded scripts to run them without a digital signature

## ByPass
- When this option is set, you can run all scripts with no warnings being displayed

## AllSigned
- When this option is set, you can only run signed scripts from trusted publishers