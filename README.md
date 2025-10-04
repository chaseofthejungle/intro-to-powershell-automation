# Intro to PowerShell Automation Overview Guide

**Description/Overview:** Microsoft PowerShell is a multi-platform (although it is intended for Windows integration) process automation and configuration management solution. It can be conceptualized as containing three components: an interactive command-line shell program, a configuration management framework, and a scripting language. For networking and systems professionals, PowerShell scripts provide automation for routine and mission-critical processes (including for remote and hybrid production environments, as an alternative to strictly on-premises device management), mitigating the odds of human error and freeing up time to work on other assignments. For activities such as implementing and reinforcing security measures, performing system maintenance, onboarding and offboarding users, adding or swapping devices (even in highly scalable environments), and routine task scheduling, the potential of PowerShell scripts is well evident.

#### Table of Contents

1. [Common Practice](#common)
2. [Cmdlets and Functions](#cmdlets)
3. [Three Common Ways to Run Executables](#executables)
4. [Supplemental Resources](#supplemental)

<hr />

## <a name="common">1. Common Practice</a>

It is common industry practice for PowerShell scripts to handle:

* File, process, service, and user management. 
* Task scheduling (PowerShell's built-in Task Scheduler can also be utilized and referenced). 
* Active Directory (AD) management.
* Executions of other scripts (e.g., batch script integration).
* Other everyday network activities.

Examples of more specific tasks that PowerShell scripts can handle include:

* Automatically scanning devices to discover, disable, and/or remove unauthorized apps.
* Automating routine maintenance tasks via the Windows Task Manager, preventing various human errors and freeing up time.
* Monitoring and optimizing processor usage to mitigate security risks and vulnerabilities, increase performance, and avoid system downtime.
* Reliably applying browser security settings and policies (e.g., cookie privacy restrictions, unauthorized downloads, password storage, unknown extensions) across systems, hardening the system against credential crackers.
* Removing unwanted apps that drain system resources (bloatware), reducing attack surface and eliminating bottlenecks.
* Dynamically improving help desk support ticket routing, delegating tickets based on rules (e.g., priority, type/nature of request, any other case-relevant details).
* Assuring that insecure protocols are not permitted for usage (another means of hardening the system).
  
<hr />

## <a name="cmdlets">2. Cmdlets and Functions</a>

PowerShell **cmdlets** are commands used for performing administrative tasks. They can access file system, registry, and other data via data providers. PowerShell 7.4 includes 1,656 pre-installed cmdlets (in comparison, PowerShell 1.0 had 129). Some purposes of cmdlets include:

* Selecting, Modifying, and Deleting Flow Permissions and Approvals.
* Selecting, Modifying, and Deleting Network Connections and Connection Permissions.
* Selecting, Adding, and Deleting URL Patterns.

PowerShell **functions** are blocks of reusable, specialized code that can be called to conduct specific tasks. They are commonly written and/or called inside of PowerShell scripts. These include both simple functions and advanced functions (which allow for various forms of parameters, including dynamic, named, positional, and switched parameters).

PowerShell **scripts** rely on cmdlets to perform sequences of operations for the purpose of process automation. Examples of common verbs at the beginning of cmdlet names include:

* *Get* (for selecting data).
  + Examples: `Get-Item`, `Get-Process`, `Get-Service`.
* *Set* (for modifying component data, such as property assignments).
  + Examples: `Set-Service`, `Set-ItemProperty`, `Set-Acl`. 
* *Remove* (for deleting data).
  + Examples: `Remove-Item`, `Remove-Service`, `Remove-Job`.

Ultimately, PowerShell script files are sets of instructions to be followed by the processor to achieve task automation.

<hr />

## <a name="executables">3. Three Common Ways to Run Executables</a>

PowerShell has *three common ways* to run standalone executables. These allow for executable files/programs to be called and used (such as ones of the popular '.exe' Windows file extension):

* The `Invoke-Expression` command: This allows strings and scripts to be executed immediately in the PowerShell session. Although more than one statement can be processed at once, strings are treated as code, so only utilizing trusted input is essential for security.
  + Full paths in command strings should be written in quotes. Arguments and options can be added after the path in the command string.
    - Common use cases for the Invoke-Expression approach include *centralized management of remote scripts for multiple servers*, *executing user-defined commands without writing to them*, *dynamic command execution* (useful for monitoring and managing system resources, evaluating data inputted by users during runtime, and making instant decisions), and *generating and executing commands based on config files and variables*.
* The `start-process` cmdlet: This provides you with control over operations, with executables running as *individual processes*. By not parsing strings directly through sessions, external code is processed more safely. Arguments and options can be added after the file name.
  + This cmdlet is often used to execute processes in the background without displaying windows (although it can also be used to stylize windows), using the `-WindowStyle Hidden` parameter. Output can be captured if you specify redirection to a location, using parameters such as `-RedirectStandardError` and `-RedirectStandardOutput`.
    - Common use cases for the start-process approach include *automating background tasks* (e.g., scheduling system backups during non-production hours, having reporting apps run hidden in the background to generate reports) and *software deployments* (e.g., automating upgrades and patches without interrupting users).
* `.\`: This is also referred to as *direct execution*, because it allows you to run a file immediately from your current working directory in PowerShell. If you need to execute a trusted, locally-stored program or script without further configuration beyond the default, this is a common sense way to do so. Any results from the program/script are immediately outputted into the console window.
  + Direct execution is performed by typing `.\` and then the file's name. You would need to be in the directory containing the file to do this. Arguments and options can be added after the file name.
    - Common use cases for the direct execution approach include *configuration updates* (retrieving settings from config files without generating new scripts for each update), *dynamic script execution* (executing commands as strings, providing real-time network configuration changes without modifying each environment's scripts), and *local script testing/troubleshooting* (especially prior to deployment).

<hr />

## <a name="supplemental">4. Supplemental Resources</a>

* *[Official Microsoft PowerShell Documentation](https://learn.microsoft.com/en-us/powershell/)*
* *[Official Microsoft Guide on Installing PowerShell on Windows](https://learn.microsoft.com/en-us/powershell/scripting/install/installing-powershell-on-windows?view=powershell-7.5)*
* *[PowerShell Gallery (Website for Distributing PowerShell Code)](https://www.powershellgallery.com/)*
