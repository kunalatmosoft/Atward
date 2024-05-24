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

These examples should help you understand how to use each command effectively in the Windows Command Prompt.