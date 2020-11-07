---
title: "Archive files to NAS via PowerShell"
author: Myles
---


I was recently tasked with implementing an automated backup solution for the output of a LIMS (Laboratory Information Management System) software. While there is a limitless number of commercial offerings available to this end, they aren't worth the time, effort or resources. I will instead use PowerShell to accomplish my goal. It's important to note that I have a limited understanding of the functionality of PowerShell, but armed with only cursory knowledge of it's utility, it seems well suited to this endeavor.


#### **Our Tasks**
<ul>
<li>&nbsp;⬜️ Archive files/folders to NAS</li>
<li>&nbsp;⬜️ Make sure as little sensitive data is exposed in the script as possible  </li>
<li>&nbsp;⬜️ Make the script run repeatedly at set intervals of time</li>
</ul>

Again, with my limited exposure to PowerShell scripting, I can confidently say the native "PowerShell IDE" known as PowerShell ISE (Integrated Scripting Environment) is superior, so that will be my development environment of choice.

It can be found within the start menu under the Windows PowerShell directory. Alternatively, pressing the Windows + r key will bring up the run prompt and you can enter`powershell_ise.exe`

**The PowerShell ISE**
![My helpful screenshot](\assets\images\post_AutoBackupNAS\PowerShell_IDE.PNG)


At it's rawest, a folder can be copied to a selected destination using [Copy-Item](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.management/copy-item?view=powershell-7) <br>For our purposes, the command should look fairly similar to this

```powershell
Copy-Item "C:\Important_LIMS_Files" -Destination "E:\IT_Internal" -Recurse -Force
```

This line is pretty self-explanatory, but to review, the first parameter is the path of the item you'd like copied. The second is the destination you would your folder copied to. The "-Recurse" option is appended to change the command to copy all directories, subdirectories and the files within your selected directory as opposed to only an empty folder. Finally, the "-Force" option force overwrites any files with the same name already existing in that directory. This is useful to us because we don't need multiple backups but rather a single most up-to-date version of the files.


#### **Our Tasks**
<ul>
<li>&nbsp;✅ Archive files/folders to NAS</li>
<li>&nbsp;⬜️ Make sure as little sensitive data is exposed in the script as possible  </li>
<li>&nbsp;⬜️ Make the script run repeatedly at set intervals of time</li>
</ul>

For my purposes and many others, accessing your NAS may require authentication. This imposes the issue of providing proper authentication to our script without leaving credentials sitting naked and afraid. My solution makes use of Task Scheduler to securely apply credentials and automate the script.

Here is how this can be achieved conceptually. A task will be created within Task Manager to run our PowerShell script at daily interval (the frequency can be adapted to your needs). When creating this task provide the  **administrative** credentials necessary to access the NAS drive. This process is outlined in the screenshots below.

![My helpful screenshot](\assets\images\post_AutoBackupNAS\taskscheduler1.PNG)
**Select Create Task**



![My helpful screenshot](\assets\images\post_AutoBackupNAS\taskscheduler2.PNG)
**Mirror these settings with exception of "Change User or Group", instead input the User/Group with NAS access**

![My helpful screenshot](\assets\images\post_AutoBackupNAS\taskscheduler3.PNG)  
**Set desired frequency for the script to run**

![My helpful screenshot](\assets\images\post_AutoBackupNAS\taskscheduler4.PNG)  
**For "Program/script:" enter**
```powershell
%SystemRoot%\syswow64\WindowsPowerShell\v1.0\powershell.exe
```
**For Add arguments (optional):**
```powershell
-NoLogo -NonInteractive -ExecutionPolicy Bypass "C:\Examples\Example\Backup_Script.ps1"
```  
**Finally select "OK"**

![My helpful screenshot](\assets\images\post_AutoBackupNAS\taskscheduler5.PNG)

**You'll be prompted to enter credentials for the account you selected previously**

![My helpful screenshot](\assets\images\post_AutoBackupNAS\taskscheduler6.PNG)

**You should see your newly created task similar to the one above**

### We've done it!
#### **Our Tasks**
<ul>
<li>&nbsp;✅ Archive files/folders to NAS</li>
<li>&nbsp;✅ Make sure as little sensitive data is exposed in the script as possible  </li>
<li>&nbsp;✅ Make the script run repeatedly at set intervals of time</li>
</ul>

<br>
## Final Notes
This is a fairly minimalist solution, but perfect for our use case. A few things worth implementing in the future, and I may very well revise this post with down the line are: multiple dated full backups, additional error checking/error logging for completion failure, an well as automation of "task scheduler" tasks directly from PowerShell.
