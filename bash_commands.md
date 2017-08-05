# Linux Notes and Commands


### What is Linux?

- Linux is an operating system that appears very similar to UNIX which is an operating system built by AT&T.
- It was created by a man named Linus Torvalds. The idea was to create an operating system that is open source unlike other operating systems that have software licenses.
- Linux comes in many flavors such as Ubuntu, which are customized versions of the operating system with additional features.
- NOTE Linux is not Unix. Linux is modelled very closely to UNIX but it is not the same operating system or an operating system built on top of UNIX.


### General Terms

- BASH - Born Again Shell
	- This is the terminal that is used to interact with the computers features, such as copying and creating files, running applications, find information about your computer, and etc.
	- Note that it is used in addition to the Operating System's GUI which is the buttons and colorful interactive environment people commonly use.


### Terminal Commands

```
pwd
```
- Print working directory - shows you your current directory (where am I currently)

```
ls
```
- Show me what is accessible from my current directory. (Where can I go, what is available to me)

```
cd
```
- Change Directory - change the folder that I'm in or currently viewing.
- **NOTE** "cd" is generally followed by the name of the directory you want to move to or a path to another directory relative to where you are currently located.

```
touch newfile.txt
```
- Touch - this command allows you to create a file that can be specified as a specific type by addding the extension.

```
cp filename.txt folderIChose
```
- Copy - the command is used to copy a file specified after "cp" as well as a directory for the copy to be stored.

```
rm filename.txt
```
- Remove/Delete - This command deletes the file from your computer

```
rm -rf folderIChose
```
- Similar to the above command, this variation allows you to remove/delete the directory specified after "-rf".

```
mkdir newFolderName
```
- Make Directory - creates a folder in your current directory.

```
man commandIwantInfoOn
```

- Manual - Command that provides an explanation and information on a command you specify

```
top
```
- Top - Shows the processes/software/applications that are consuming the most CPU.

```
ps
```
-  Basic Command viewing the processes running on the system. It provides a snapshot of the current processes along with detailed information like user id, cpu usage, memory usage, command name etc.

```
shutdown [-r , -h] [+60, now, etc.]
```

- The command allows you to power off the computer. The command takes two arguments which indicate restart or turn off. The next argument is a time which can be "now" or "+" with a number of minutes to wait until the command is executed.

### Cron Jobs / Crontab

-Crontab is a program that allows the user to schedule jobs/processes you would like to have executed automatically at a specified time.
- For example, you can set up a job that will run every month and backup your files to a folder somewhere

```
sudo crontab -e
```
- Opens a text file in your editor. Generally "vim".
- This is where you will set up a schedule of processes you would like to run at the specified times.
-Example Job:
```
# minute hour dayOfMonth month dayOfWeek command
* * * * 0 /usr/bin/local/python3 updateCsv.py
```
- Each line in the file represents a job that will run.
- In the example above, your machine will run at any minute, hour, day of month, or month ON A SUNDAY updateCsv.py using the python3 interpreter located at the file path specified. "0" here represents Sunday. Each one of these parameters expect either an * or a number within a range.


### TAR

- Tar is program in Linux machines that allow you to back up files on your machine to folder of your choosing.


#### Creating a .tar or .tar.gz backup
```
sudo tar -cvpzf backup.tar.gz --exclude=/Desktop/longVideosFolder /Desktop
```

- The above creates a "tar ball" or compressed tar file that contains the contents of the repository Desktop, excluding the contents of the folder longVideosFolder.
- c = create a file or overwrite, v = verbose or display files being copied in terminal, p = keep permisions associated with backup, z = zip the file or produce .gz file, f = provide file name for backup of files.
- --exclude allows you to exclude certain files from the back up. (Not Required)
- The final parameter is what to back up.

#### Unpacking a .tar or .tar.gz backup

```
sudo tar -xvpzf backup.tar.gz -C /folderDestination
```

- Similar to the creation command, this allows you to unpack the contents of the file into the folder of your choice.
- NOTE x = extract, "z" is only used if the file you are unpacking is a .gz file. 
