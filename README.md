## CMD

Below, I provide examples of how to use each command in the Windows Command Prompt (cmd). This will help you understand how each command can be implemented and used effectively.

### File and Directory Management Commands

```cmd
:: Display or modify file extension associations
assoc
assoc .txt=txtfile

:: Display or change file attributes
attrib +r myfile.txt
attrib -r myfile.txt

:: Display the name of or change the current directory
cd
cd C:\Users\YourName\Documents

:: Clear the screen
cls

:: Copy one or more files to another location
copy file1.txt file2.txt
copy C:\source\file.txt D:\destination\

:: Delete one or more files
del file1.txt
erase file1.txt

:: Display a list of files and subdirectories in a directory
dir
dir /w /p

:: Display messages, or turn command echoing on or off
echo Hello, World!
echo off

:: Quit the CMD.EXE program (command interpreter)
exit

:: Compare two files or sets of files, and display the differences
fc file1.txt file2.txt

:: Search for a text string in a file or files
find "Hello" file.txt
find /i "Hello" *.txt

:: Search for strings in files
findstr "pattern" file.txt

:: Run a specified command for each file in a set of files
for %f in (*.txt) do type %f

:: Display or modify file types used in file extension associations
ftype
ftype txtfile="C:\Windows\System32\NOTEPAD.EXE" %1

:: Create a new directory
md NewDirectory
mkdir NewDirectory

:: Move one or more files from one directory to another directory
move file.txt C:\NewFolder\

:: Remove a directory
rd OldDirectory
rmdir OldDirectory

:: Rename a file or files
ren oldname.txt newname.txt
rename oldname.txt newname.txt

:: Replace files
replace newfile.txt C:\TargetDirectory\

:: Robust file copy for Windows
robocopy C:\Source C:\Destination /MIR

:: Graphically display the directory structure of a drive or path
tree

:: Display the contents of a text file
type file.txt

:: Copy files and directory trees
xcopy C:\Source C:\Destination /E /I
```

### System Information and Configuration Commands

```cmd
:: Set or clear extended CTRL+C checking
break

:: Call one batch program from another
call secondbatch.bat

:: Display or set the active code page number
chcp
chcp 65001

:: Check a disk and display a status report
chkdsk C:
chkdsk C: /f

:: Display or modify the checking of disk at boot time
chkntfs C:
chkntfs /d

:: Set the default console foreground and background colors
color 0A

:: Compare the contents of two files or sets of files
comp file1.txt file2.txt

:: Display or set the date
date
date 05-24-2024

:: Edit command lines, recall Windows commands, and create macros
doskey

:: Display a list of all installed device drivers and their properties
driverquery

:: Display Group Policy information for machine or user
gpresult /R

:: Display the host name portion of the full computer name
hostname

:: Configure a system device
mode con:cols=120 lines=30

:: Display output one screen at a time
more file.txt

:: Display files opened by remote users for a file share
openfiles

:: Display or set a search path for executable files
path
path C:\Program Files\MyApp;C:\Windows\System32

:: Suspend processing of a batch file and display a message
pause

:: Restore the previous value of the current directory saved by pushd
popd

:: Change the Windows command prompt
prompt $P$G

:: Save the current directory then change it
pushd C:\NewDirectory

:: Configure and manage custom recovery images
recimg /createimage C:\RefreshImage

:: Recover readable information from a bad or defective disk
recover file.txt

:: Communicate with the Service Control Manager and services
sc query
sc start servicename

:: Schedule commands and programs to run on a computer
schtasks /create /sc daily /tn MyTask /tr "C:\MyScript.bat" /st 12:00

:: Display, set, or remove environment variables
set
set MYVAR=MyValue

:: Begin localization of environment changes in a batch file
setlocal

:: Display machine-specific properties and configuration
systeminfo

:: Display all currently running tasks, including services
tasklist

:: Kill or stop a running process or application
taskkill /PID 1234 /F

:: Display or set the system time
time
time 14:30

:: Wait for a specified amount of time, or until a key is pressed
timeout /t 10

:: Set the window title for a CMD.EXE session
title My Command Prompt

:: Display the Windows version
ver

:: Tell Windows whether to verify that your files are written correctly to a disk
verify
verify on

:: Display a disk volume label and serial number
vol
```

### Networking Commands

```cmd
:: Transfer files to and from a remote computer
ftp ftp.example.com

:: Display the MAC address for network adapters
getmac

:: Display IP network configuration values
ipconfig
ipconfig /all

:: Manage network resources
net use Z: \\server\share
net user username password /add

:: Display network statistics and current TCP/IP network connections
netstat
netstat -an

:: Query Internet domain name servers
nslookup example.com

:: Trace the route to a remote host and report packet loss
pathping example.com

:: Send ICMP ECHO_REQUEST packets to network hosts
ping example.com

:: Display and modify the IP routing table
route print
route add 192.168.1.0 mask 255.255.255.0 192.168.1.1

:: Trace the route taken by packets to reach a network host
tracert example.com
```

### Disk Management Commands

```cmd
:: Manage disk partitions
diskpart

:: Format a disk for use with Windows
format D: /FS:NTFS

:: Create, change, or delete the volume label of a disk
label D: MyLabel

:: Manage a volume mount point
mountvol

:: Associate a path with a drive letter
subst X: C:\Path
```

### Advanced Commands

```cmd
:: Display or modify file extension associations
assoc
assoc .txt=txtfile

:: Display or alter the encryption of directories (files) and display the encryption status of files and directories
cipher /e /s:C:\MyFolder
cipher /d /s:C:\MyFolder

:: Display or alter the compression of files and directories on NTFS partitions
compact /c C:\MyFolder
compact /u C:\MyFolder

:: Convert FAT volumes to NTFS. You cannot convert the current drive
convert D: /FS:NTFS

:: Display a list of all installed device drivers and their properties
driverquery

:: Perform tasks that are related to file systems or dismount volumes
fsutil

:: Refresh Group Policy settings
gpupdate /force

:: Update the Performance counter registry values and explain text for service
lodctr /R

:: Query, display, or disconnect open files
openfiles /query

:: Query, add, delete, and change registry keys and values
reg query HKLM\Software
reg add HKLM\Software\MyKey /v MyValue /t REG_SZ /d MyData
reg delete HKLM\Software\MyKey /v MyValue

:: Communicate with the Service Control Manager and services
sc query
sc start servicename

:: Shut down or restart a local or remote computer
shutdown /s /t 0
shutdown /r /t 0

:: Display a list of currently running processes on a local or remote computer
tasklist

:: Kill or stop a running process or application
taskkill /PID 1234 /F

:: Write performance data to the command window or to a log file
typeperf "\Processor(_Total)\% Processor Time" -sc 5

:: Display and configure Volume Shadow Copy Services
vssadmin list shadows

:: Backup and restore your operating system, volumes, files, folders, and applications from a command prompt
wbadmin start backup -backupTarget:D: -include:C: -allCritical -quiet

:: Retrieve information about event logs and publishers
wevtutil qe Application /f:text

:: Display WMI information inside an interactive command shell
wmic
```

### Batch Scripting Commands

```cmd
:: Perform conditional processing in batch programs
if exist file.txt echo File exists

:: Directs the Windows command interpreter to a labeled line in a batch program
goto MyLabel

:: Call one batch program from another
call mybatch.bat

:: Quit the CMD.EXE program (command interpreter)
exit

:: Run a specified command for each file in a set of files
for %%f in (*.txt) do echo %%f

:: Suspend processing of a batch file and display a message
pause

:: Record comments (remarks) in batch files or at the command prompt
rem This is a comment

:: Begin localization of environment changes in a batch file
setlocal

:: End localization of environment changes in a batch file
endlocal
```

Sure, here is a comprehensive list of Command Prompt commands, their implementations, and explanations. This should cover a wide range of commands available in the Windows Command Prompt.

### File and Directory Management Commands

```cmd
assoc
```
**Description**: Displays or modifies file extension associations.
```cmd
assoc .txt
```
**Explanation**: Displays the current file association for `.txt` files.

```cmd
attrib
```
**Description**: Displays or changes file attributes.
```cmd
attrib +r -s -h example.txt
```
**Explanation**: Sets the file `example.txt` as read-only, removes the system and hidden attributes.

```cmd
cd or chdir
```
**Description**: Displays the name of or changes the current directory.
```cmd
cd \Users\YourName\Documents
```
**Explanation**: Changes the current directory to `\Users\YourName\Documents`.

```cmd
cls
```
**Description**: Clears the screen.
```cmd
cls
```
**Explanation**: Clears all previous commands and outputs from the Command Prompt window.

```cmd
copy
```
**Description**: Copies one or more files to another location.
```cmd
copy example.txt D:\Backup\
```
**Explanation**: Copies `example.txt` to the `D:\Backup\` directory.

```cmd
del or erase
```
**Description**: Deletes one or more files.
```cmd
del example.txt
```
**Explanation**: Deletes the file `example.txt`.

```cmd
dir
```
**Description**: Displays a list of files and subdirectories in a directory.
```cmd
dir
```
**Explanation**: Lists all files and directories in the current directory.

```cmd
echo
```
**Description**: Displays messages, or turns command echoing on or off.
```cmd
echo Hello, World!
```
**Explanation**: Displays the message `Hello, World!`.

```cmd
exit
```
**Description**: Quits the CMD.EXE program (command interpreter).
```cmd
exit
```
**Explanation**: Closes the Command Prompt window.

```cmd
fc
```
**Description**: Compares two files or sets of files, and displays the differences.
```cmd
fc file1.txt file2.txt
```
**Explanation**: Compares `file1.txt` and `file2.txt`, displaying their differences.

```cmd
find
```
**Description**: Searches for a text string in a file or files.
```cmd
find "search text" example.txt
```
**Explanation**: Searches for the string `search text` in the file `example.txt`.

```cmd
findstr
```
**Description**: Searches for strings in files.
```cmd
findstr "search text" *.txt
```
**Explanation**: Searches for the string `search text` in all `.txt` files in the current directory.

```cmd
for
```
**Description**: Runs a specified command for each file in a set of files.
```cmd
for %f in (*.txt) do echo %f
```
**Explanation**: Displays the name of each `.txt` file in the current directory.

```cmd
ftype
```
**Description**: Displays or modifies file types used in file extension associations.
```cmd
ftype txtfile="C:\Program Files\Notepad++\notepad++.exe" "%1"
```
**Explanation**: Sets the program Notepad++ to open `.txt` files.

```cmd
md or mkdir
```
**Description**: Creates a new directory.
```cmd
mkdir NewFolder
```
**Explanation**: Creates a directory named `NewFolder`.

```cmd
move
```
**Description**: Moves one or more files from one directory to another directory.
```cmd
move example.txt D:\NewFolder\
```
**Explanation**: Moves the file `example.txt` to the `D:\NewFolder\` directory.

```cmd
rd or rmdir
```
**Description**: Removes a directory.
```cmd
rmdir /s /q NewFolder
```
**Explanation**: Removes the directory `NewFolder` and its contents without confirmation.

```cmd
ren or rename
```
**Description**: Renames a file or files.
```cmd
rename example.txt newexample.txt
```
**Explanation**: Renames `example.txt` to `newexample.txt`.

```cmd
replace
```
**Description**: Replaces files.
```cmd
replace newexample.txt D:\Backup\
```
**Explanation**: Replaces files in the `D:\Backup\` directory with `newexample.txt`.

```cmd
robocopy
```
**Description**: Robust file copy for Windows.
```cmd
robocopy C:\Source D:\Destination /MIR
```
**Explanation**: Copies all files and directories from `C:\Source` to `D:\Destination`, mirroring the directory structure.

```cmd
tree
```
**Description**: Graphically displays the directory structure of a drive or path.
```cmd
tree
```
**Explanation**: Displays the directory tree of the current directory.

```cmd
type
```
**Description**: Displays the contents of a text file.
```cmd
type example.txt
```
**Explanation**: Displays the contents of `example.txt`.

```cmd
xcopy
```
**Description**: Copies files and directory trees.
```cmd
xcopy C:\Source D:\Destination /E /H /C /I
```
**Explanation**: Copies all files and directories (including hidden and empty directories) from `C:\Source` to `D:\Destination`.

### System Information and Configuration Commands

```cmd
break
```
**Description**: Sets or clears extended CTRL+C checking.
```cmd
break on
```
**Explanation**: Enables extended CTRL+C checking in CMD.EXE.

```cmd
call
```
**Description**: Calls one batch program from another.
```cmd
call secondbatch.bat
```
**Explanation**: Runs the batch file `secondbatch.bat` from another batch file.

```cmd
chcp
```
**Description**: Displays or sets the active code page number.
```cmd
chcp 65001
```
**Explanation**: Changes the active code page to UTF-8.

```cmd
chkdsk
```
**Description**: Checks a disk and displays a status report.
```cmd
chkdsk C: /F /R
```
**Explanation**: Checks the C: drive for errors and repairs them.

```cmd
chkntfs
```
**Description**: Displays or modifies the checking of disk at boot time.
```cmd
chkntfs /D
```
**Explanation**: Restores the default setting for automatic file checking at boot time.

```cmd
color
```
**Description**: Sets the default console foreground and background colors.
```cmd
color 0A
```
**Explanation**: Changes the text color to green and the background to black.

```cmd
comp
```
**Description**: Compares the contents of two files or sets of files.
```cmd
comp file1.txt file2.txt
```
**Explanation**: Compares `file1.txt` and `file2.txt`.

```cmd
date
```
**Description**: Displays or sets the date.
```cmd
date
```
**Explanation**: Displays the current date and prompts for a new date.

```cmd
doskey
```
**Description**: Edits command lines, recalls Windows commands, and creates macros.
```cmd
doskey /history
```
**Explanation**: Displays a history of commands entered in the current session.

```cmd
driverquery
```
**Description**: Displays a list of all installed device drivers and their properties.
```cmd
driverquery
```
**Explanation**: Lists all device drivers installed on the system.

```cmd
fc
```
**Description**: Compares two files or sets of files, and displays the differences.
```cmd
fc file1.txt file2.txt
```
**Explanation**: Compares `file1.txt` and `file2.txt`.

```cmd
gpresult
```
**Description**: Displays Group Policy information for machine or user.
```cmd
gpresult /R
```
**Explanation**: Displays the Resultant Set of Policy (RSoP) summary for the current user and computer.

```cmd
hostname
```
**Description**: Displays the host name portion of the full computer name.
```cmd
hostname
```
**Explanation**: Displays the computer's hostname.

```cmd
mode
```
**Description**: Configures a system device.
```cmd
mode con: cols=80 lines=25
```
**Explanation**: Sets the Command Prompt window to 80 columns and 25 lines.

```cmd
more
```
**Description**: Displays output one screen at a time.
```cmd
type example.txt | more
```
**Explanation**: Displays the contents of `example.txt` one page at a time.

```cmd
openfiles
```
**Description**: Displays files opened by remote users for a file share.
```cmd
openfiles /query
```
**Explanation**: Displays open files and their associated users.

```cmd
path
```
**Description**: Displays or sets a search path for executable files.
```cmd
path
```
**Explanation**: Displays the current search path.

```cmd
pause
```
**Description**: Suspends processing of a batch file and displays a message.
```cmd
pause
```
**Explanation**: Pauses

 the execution of a batch file and displays the message "Press any key to continue...".

```cmd
popd
```
**Description**: Restores the previous value of the current directory saved by `pushd`.
```cmd
popd
```
**Explanation**: Changes to the directory saved by the last `pushd`.

```cmd
prompt
```
**Description**: Changes the Windows command prompt.
```cmd
prompt $P$G
```
**Explanation**: Changes the command prompt to display the current directory followed by a `>` sign.

```cmd
pushd
```
**Description**: Saves the current directory then changes it.
```cmd
pushd D:\Projects
```
**Explanation**: Saves the current directory and changes to `D:\Projects`.

```cmd
recimg
```
**Description**: Configures and manages custom recovery images.
```cmd
recimg /createimage D:\RefreshImage
```
**Explanation**: Creates a custom recovery image in `D:\RefreshImage`.

```cmd
recover
```
**Description**: Recovers readable information from a bad or defective disk.
```cmd
recover example.txt
```
**Explanation**: Attempts to recover readable information from `example.txt`.

```cmd
sc
```
**Description**: Communicates with the Service Control Manager and services.
```cmd
sc query
```
**Explanation**: Displays the status of all services.

```cmd
schtasks
```
**Description**: Schedules commands and programs to run on a computer.
```cmd
schtasks /create /tn "Backup" /tr "backup.bat" /sc daily /st 23:00
```
**Explanation**: Schedules a task named "Backup" to run `backup.bat` daily at 11 PM.

```cmd
set
```
**Description**: Displays, sets, or removes environment variables.
```cmd
set PATH=C:\Program Files\NewPath;%PATH%
```
**Explanation**: Adds `C:\Program Files\NewPath` to the system's PATH environment variable.

```cmd
setlocal
```
**Description**: Begins localization of environment changes in a batch file.
```cmd
setlocal
```
**Explanation**: Begins localization in a batch file, preserving the current environment variables.

```cmd
systeminfo
```
**Description**: Displays machine-specific properties and configuration.
```cmd
systeminfo
```
**Explanation**: Displays detailed system configuration information for the computer.

```cmd
tasklist
```
**Description**: Displays all currently running tasks, including services.
```cmd
tasklist
```
**Explanation**: Lists all running processes.

```cmd
taskkill
```
**Description**: Kills or stops a running process or application.
```cmd
taskkill /im notepad.exe /f
```
**Explanation**: Forces the termination of all instances of `notepad.exe`.

```cmd
time
```
**Description**: Displays or sets the system time.
```cmd
time
```
**Explanation**: Displays the current system time and prompts for a new time.

```cmd
timeout
```
**Description**: Waits for a specified amount of time, or until a key is pressed.
```cmd
timeout /t 10
```
**Explanation**: Waits for 10 seconds before continuing.

```cmd
title
```
**Description**: Sets the window title for a CMD.EXE session.
```cmd
title My Custom Command Prompt
```
**Explanation**: Sets the Command Prompt window title to "My Custom Command Prompt".

```cmd
ver
```
**Description**: Displays the Windows version.
```cmd
ver
```
**Explanation**: Displays the current version of Windows.

```cmd
verify
```
**Description**: Tells Windows whether to verify that your files are written correctly to a disk.
```cmd
verify on
```
**Explanation**: Turns on file verification.

```cmd
vol
```
**Description**: Displays a disk volume label and serial number.
```cmd
vol
```
**Explanation**: Displays the volume label and serial number for the current drive.

### Networking Commands

```cmd
ftp
```
**Description**: Transfers files to and from a remote computer.
```cmd
ftp ftp.example.com
```
**Explanation**: Connects to an FTP server at `ftp.example.com`.

```cmd
getmac
```
**Description**: Displays the MAC address for network adapters.
```cmd
getmac
```
**Explanation**: Lists the MAC addresses of all network adapters on the system.

```cmd
ipconfig
```
**Description**: Displays IP network configuration values.
```cmd
ipconfig /all
```
**Explanation**: Displays detailed IP configuration information for all adapters.

```cmd
net
```
**Description**: Manages network resources.
```cmd
net view
```
**Explanation**: Displays a list of computers in the current domain or workgroup.

```cmd
netstat
```
**Description**: Displays network statistics and current TCP/IP network connections.
```cmd
netstat -an
```
**Explanation**: Displays all active connections and listening ports, numerically.

```cmd
nslookup
```
**Description**: Queries Internet domain name servers.
```cmd
nslookup example.com
```
**Explanation**: Queries the DNS to find the IP address associated with `example.com`.

```cmd
pathping
```
**Description**: Traces the route to a remote host and reports packet loss.
```cmd
pathping example.com
```
**Explanation**: Traces the route to `example.com` and reports on packet loss at each hop.

```cmd
ping
```
**Description**: Sends ICMP ECHO_REQUEST packets to network hosts.
```cmd
ping example.com
```
**Explanation**: Sends a ping request to `example.com` to check connectivity.

```cmd
route
```
**Description**: Displays and modifies the IP routing table.
```cmd
route print
```
**Explanation**: Displays the current routing table.

```cmd
tracert
```
**Description**: Traces the route taken by packets to reach a network host.
```cmd
tracert example.com
```
**Explanation**: Displays the route taken to reach `example.com`.

### Disk Management Commands

```cmd
diskpart
```
**Description**: Manages disk partitions.
```cmd
diskpart
```
**Explanation**: Opens the DiskPart command interpreter.

```cmd
format
```
**Description**: Formats a disk for use with Windows.
```cmd
format D: /FS:NTFS
```
**Explanation**: Formats the D: drive with the NTFS file system.

```cmd
label
```
**Description**: Creates, changes, or deletes the volume label of a disk.
```cmd
label D: BackupDrive
```
**Explanation**: Sets the label of the D: drive to `BackupDrive`.

```cmd
mountvol
```
**Description**: Manages a volume mount point.
```cmd
mountvol D: /D
```
**Explanation**: Removes the volume mount point from drive D:.

```cmd
subst
```
**Description**: Associates a path with a drive letter.
```cmd
subst X: C:\Path\To\Folder
```
**Explanation**: Maps `C:\Path\To\Folder` to the virtual drive X:.

### Advanced Commands

```cmd
assoc
```
**Description**: Displays or modifies file extension associations.
```cmd
assoc .txt=txtfile
```
**Explanation**: Associates the `.txt` extension with the `txtfile` file type.

```cmd
cipher
```
**Description**: Displays or alters the encryption of directories (files) and displays the encryption status of files and directories.
```cmd
cipher /e /s:C:\Secure
```
**Explanation**: Encrypts all files in the directory `C:\Secure`.

```cmd
compact
```
**Description**: Displays or alters the compression of files and directories on NTFS partitions.
```cmd
compact /c /s:C:\MyFiles
```
**Explanation**: Compresses all files in the directory `C:\MyFiles`.

```cmd
convert
```
**Description**: Converts FAT volumes to NTFS. You cannot convert the current drive.
```cmd
convert D: /FS:NTFS
```
**Explanation**: Converts the D: drive to NTFS.

```cmd
driverquery
```
**Description**: Displays a list of all installed device drivers and their properties.
```cmd
driverquery
```
**Explanation**: Lists all installed device drivers.

```cmd
fsutil
```
**Description**: Performs tasks that are related to file systems or dismount volumes.
```cmd
fsutil dirty query C:
```
**Explanation**: Queries the dirty bit on the C: drive.

```cmd
gpupdate
```
**Description**: Refreshes Group Policy settings.
```cmd
gpupdate /force
```
**Explanation**: Forces a refresh of Group Policy settings.

```cmd
lodctr
```
**Description**: Updates the Performance counter registry values and explain text for a service.
```cmd
lodctr /R
```
**Explanation**: Rebuilds the performance counter registry settings and values.

```cmd
openfiles
```
**Description**: Queries, displays, or disconnects open files.
```cmd
openfiles /query
``**
Explanation**: Displays open files and their associated users.

```cmd
reg
```
**Description**: Queries, adds, deletes, and

 edits registry entries.
```cmd
reg query HKLM\Software
```
**Explanation**: Queries the `HKLM\Software` registry key.

```cmd
sc
```
**Description**: Communicates with the Service Control Manager and services.
```cmd
sc query
```
**Explanation**: Displays the status of all services.

```cmd
schtasks
``**
Description**: Schedules commands and programs to run on a computer.
```cmd
schtasks /create /tn "Backup" /tr "backup.bat" /sc daily /st 23:00
``**
Explanation**: Schedules a task named "Backup" to run `backup.bat` daily at 11 PM.

```cmd
shutdown
``**
Description**: Shuts down or restarts a computer.
```cmd
shutdown /s /f /t 0
``**
Explanation**: Shuts down the computer immediately, forcing applications to close.

```cmd
sfc
``**
Description**: Scans and verifies the integrity of all protected system files and replaces incorrect versions with correct Microsoft versions.
```cmd
sfc /scannow
``**
Explanation**: Scans and repairs protected system files.

```cmd
tasklist
``**
Description**: Displays all currently running tasks, including services.
```cmd
tasklist
``**
Explanation**: Lists all running processes.

```cmd
taskkill
``**
Description**: Kills or stops a running process or application.
```cmd
