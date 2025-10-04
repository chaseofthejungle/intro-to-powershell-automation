# Intro to PowerShell Automation Overview Guide

**TODO:** An introductory guide to PowerShell's potential for systems automation.

**Description/Overview:** Microsoft PowerShell is a multi-platform (although it is intended for Windows integration) process automation and configuration management solution. It can be conceptualized as containing three components: an interactive command-line shell program, a configuration management framework, and a scripting language. For networking and systems professionals, PowerShell scripts provide automation for routine and mission-critical processes (including for remote and hybrid production environments, as an alternative to strictly on-premises device management), mitigating the odds of human error and freeing up time to work on other assignments. For activities such as implementing and reinforcing security measures, performing system maintenance, onboarding and offboarding users, adding or swapping devices (even in highly scalable environments), and routine task scheduling, the potential of PowerShell scripts is well evident.

<hr />

## 1. Common Practice

It is common industry practice for PowerShell scripts to handle:

* File, Process, Service, and User Management. 
* Task Scheduling (PowerShell's built-in Task Scheduler can also be utilized and referenced). 
* Active Directory (AD) Management.
* Executions of Other Scripts (e.g., batch script integration).
* Other Common Network Activities.

<hr />

## 2. Cmdlets, Functions, and Executable Commands

PowerShell **cmdlets** are commands used for performing administrative tasks. They can access file system, registry, and other data via data providers. PowerShell 7.4 includes 1,656 pre-installed cmdlets (in comparison, PowerShell 1.0 had 129). Some purposes of cmdlets include:

* Selecting, Modifying, and Deleting Flow Permissions and Approvals.
* Selecting, Modifying, and Deleting Network Connections and Connection Permissions.
* Selecting, Adding, and Deleting URL Patterns.

PowerShell **functions** are blocks of reusable, specialized code that can be called to conduct specific tasks. They are commonly written and/or called inside of PowerShell scripts. These include both simple functions and advanced functions (which allow for various forms of parameters, including dynamic, named, positional, and switched parameters).

Powershell's standalone **executable commands** allow for executable files/programs to be called and used (such as ones of the popular '.exe' Windows file extension). Three commands used to run executable files in PowerShell include `invoke-expression`, `start-process`, and `.\`.

PowerShell **scripts** rely on cmdlets to perform sequences of operations for the purpose of process automation. Examples of common verbs at the beginning of cmdlet names include:

* *Get* (for selecting data).
  + Examples: `Get-Item`, `Get-Process`, `Get-Service`.
* *Set* (for modifying component data, such as property assignments).
  + Examples: `Set-Service`, `Set-ItemProperty`, `Set-Acl`. 
* *Remove* (for deleting data).
  + Examples: `Remove-Item`, `Remove-Service`, `Remove-Job`.

Ultimately, PowerShell script files are sets of instructions to be followed by the processor to achieve task automation.

<hr />

## 3. Supplemental Resources

* *[Official Microsoft PowerShell Documentation](https://learn.microsoft.com/en-us/powershell/)*
* *[Official Microsoft Guide on Installing PowerShell on Windows](https://learn.microsoft.com/en-us/powershell/scripting/install/installing-powershell-on-windows?view=powershell-7.5)*
* *[PowerShell Gallery (Website for Distributing PowerShell Code)](https://www.powershellgallery.com/)*
