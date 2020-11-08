---
title: "Distillation of a YouTube PowerShell Tutorial"
author: Myles
---

I've heard often that PowerShell is best learned through experience. Select an interesting project, work through it, and learn from the ensuing struggles. Keeping that in mind, I still see value in building a foundational knowledge of the Language. I was recommended the [Busy Ping](https://www.youtube.com/playlist?list=PL4SEtvjUqihGdXEQbsKFHOXTswqdqCE2X) PowerShell Tutorial series so that is where we will begin our journey.

 My intention for this post is to review, document, and dissect the more essential information covered in the series for later reference. The series spans 13 video and will be broken down in similar fashion.

<br>

## PowerShell Tutorial | 001 | Introduction

**What is PowerShell?**

| :---        |    :---   |
| **An Automation Framework?**   | **Yes** |
| **A Complete Replacement for Command Prompt?**   | **No**        |
| **A Full fledge Programming Language?**   | **No** --- *Though Debatable IMO*      |
| **Strong Querying & Reporting Tool?** | **Yes** |

<br>

## PowerShell Tutorial | 002 | PowerShell Release History
**The Current PowerShell version at the time of writing this is 5.1.19041.546** - Your version can be found by running
```powershell
$PSVersionTable
```

<br>

## PowerShell Tutorial | 003 | Navigating PowerShell
**By default, both a 32bit - [Windows PowerShell (x86)] & a 64 bit [Windows PowerShell] are installed**

<br>

## PowerShell Tutorial | 004 | Basic usage and commands
Much like the Linux CLI aliases can be created. An alias is a custom shortcut made to represent a different command. Below is an example of how to create one and how they function.

```powershell
New-Alias -Name "List" Get-ChildItem
```
By running this command "list" has been created as an alias for the "Get-ChildItem" command, that is to say entering "list" will instead run "Get-ChildItem" under the hood until that PowerShell session is closed. This was also an example of a temporary alias, but permanent aliases can also be created.


| PowerShell Commands | Aliases with equivalent to Linux's |
| :----:        |    :----:   |
| ```Get-ChildItem``` or ```dir``` in cmd  | ```ls``` |
| ```New-Item``` + few [notes](https://stackoverflow.com/questions/50832054/mkdir-vs-new-item-is-it-the-same-cmdlets) | ```mkdir``` |
| ```Get-Processes``` | ```ps``` |

<br>

| PowerShell Commands | Aliases specific to PowerShell |
| :----:        |    :----:   |
| ```Get-Alias``` | ```alias``` |
| ```Get-Commands``` | ```gcm``` |

### Notes
- |Verb Dash Hyphen| aka "Get-Help" syntax is used for all PowerShell commands.
- These verb dash hyphen commands are known and referred to as Cmdlets.





## PowerShell Tutorial | 005 | Upgrading PowerShell
Mostly irrelevant information as the series is pretty dated, instead I'll leave a link to upgrade PowerShell 7.0 the most current release. | [PowerShell 7.0](https://docs.microsoft.com/en-us/powershell/scripting/install/migrating-from-windows-powershell-51-to-powershell-7?view=powershell-7) | This will install alongside PowerShell 5.0 leaving both versions functional.

<br>

## PowerShell Tutorial | 006 | Cmdlets and Aliases - Part 1
For aliases refer to table in [PowerShell Tutorial | 004 |]

<br>
## PowerShell Tutorial | 007 | Using Help in PowerShell
Get-Help will provide partial information about the a Cmdlet. For the unabridged version of "Get-Help", "Update-Help" must be run. "Update-Help" will download the full version of the help files on your machine - must be run in administrative PowerShell terminal. *This is worth doing, especially when starting out*
