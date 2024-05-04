# Linux-commands

Launch the machine using below url:
https://bellard.org/jslinux/

1. Display name of current logged-in user --> whoami
2. Check system date or time --> date or
3. Display only date --> date %D
4. Display only time(hour,min,sec) --> date %T
5. Display only hour and minute --> date %H:%M
6. Display files and folders in the human readable format --> ls -lh
7. Clean the screen --> ctrl+l or clear
## Creating, Deleting and Editing 
8. Read a file and search
less <file>
For top to bottom: use /<search_keyword> and click 'n' for next
For bottom to top search: use ?<search_keyword> and click 'n' for next
use 'shift + g' for moving to last line directly and go back to the first line just click 'p'
9. View content of a file page by page --> more <file>
 use down arrow for next page
10. Absolute path --> /home/pra-y/myfolder/newfolder
11. Relative Path --> myfolder/newfolder
## Linux head & tail commands
12. Read or display top 5 lines of file --> head -5 <file>
13. Read or display bottom 5 lines of file --> tail -5 <file>
14. Sort a file --> sort <file> or sort -r <file>
15. Display unique content of file --> sort <file> | uniq
16. A file has 9 lines and how to split this file in 3 different files --> split -l 3 <file>
## Grep, Egrep Command
17. Search a word or string and display matching content from file --> grep "word" <file>
18. Search multiple words and display matching content from file --> egrep "word1|WORD2" <file>
19. How to use WILDCARDS in linux *,[],{} -->
ls file\*  For e.g. - ls *.csv
touch file {1..5}  For e.g.- touch file{1..5}
20. Shuffle content of file --> shuf <file>
21. Count no. of line in a file --> wc -l <file>
22. Check if two files are identical --> cmp fileA fileB
23. Compare and display difference b/w two files --> diff -u fileA fileB
## Search files in linux
24. Find a file
Method1: find /path/ -name <file>
Method2: First install locate
'sudo updatedb' then Run 'locate <file>'
25. Read or get more info about command --> man ls or ls --help | more
26. Check which executable is using for a command --> which ls
27. Use calculator in linux --> bc
28. Check calendar of month or year --> cal or cal JAN 2023 or cal 2024
29. Check how long server has been running --> uptime
30. Record your activity on terminal in a file --> script & ctrl + d for exit
31. Create a shortcut of long command --> alias l="ls -ltr" && alias -p
## Compress and decompress the files and folders
32. Compress the file --> gzip -k <file>
33. Decompress the file --> gzip -d <file> or gunzip <file>
34. Compress a folder --> tar -czf <file_name>.tar.gz <file_name>
35. Decompress a folder --> tar -xzf <file_name>.tar.gz
36. Compress multiple files in one zipped file --> zip <file_name>.zip file1 file2 file3
37. Decompress the same zipped file --> unzip <file_name>.zip
38. List files in zipped file --> zip -l <file_name>.zip
## Downloading files from Internet
39. Download a file from internet --> wget <url_of_file> or wget -O <folder_name> <url_of_file>
40. How to call an API --> curl <url_of_file/pkg>
41. Check if an application is installed or not --> rpm -qa | grep <pkg_name> or dnf list installed | grep <pkg_name>
42. List available pkgs to install --> apt search <package_name> or yum/dnf list available
43. Start/Stop a service --> systemctl start/stop/restart <service_name>
44. List all the services --> systemctl list-units --type=service --all
45. List all existing environment variables --> printenv
46. How to add a new environment variable
export JAVA_HOME="/usr/lib/jvm/java_v"
export PATH=$JAVA_HOME/bin:$PATH
47. How to add new environment variables permanently for a specific user
Add new variable in ~/.bashrc
source ~/.bashrc
48. Print a specific column of csv file --> awk -F , '{print $1,$2}' <file_name>.csv
Last column -->    awk -F , '{print $NF}' <file_name>.csv
49. Display starting two characters of all lines --> cut -c1-2 <file_name>.txt (print the first and second char)
50. Display a specific line from a file --> sed -n '5p' <file_name>.txt
51. Replace a specific word temporary within a file --> sed 's/from/to/g' <file_name>.txt
52. Covert the content to uppercase or lowercase within a file -->
tr [:lower:] [:upper:] <file.txt
tr [:punct:] Z <file.txt
tr [:digit:] Z <file.txt
Let's take a test.txt for example and has content given below:
    UpperCase Letter
    LowerCase Letter
    Punct - $%@#&
    Digit -12345
tr -d % <test.text
tr "%" "^" < test.txt
53. How to extend or shrink the size of file --> truncate -s 100M file.txt
54. Display follwing line in vertical line --> echo "ABCDE" | fold -w1
55. Change user or login as different user --> su <username>
## Access Remote servers
56. Access remote linux server --> ssh username@ip/hostname
57. Copy a file to remote server --> scp <file_name> username@hostname:/tmp/
58. Change the user ownership of file --> sudo chown <owner_name> <file_name>
59. Change Group ownership of file --> sudo chgrp <group_name> <file_name>
* sudo chown user_name:group_name <file_name>
## Memory INFO
60. How to check memory of system like available or swap --> free -th
61. How to check % Memory and CPU utilization --> top
62. Check disk utilization --> du -h <folder_name>
63. How to check filesystem available and disk space allocated --> df -h
## System INFO
64. Check cpu/core/thread info of machine --> lscpu && arch && cat /proc/cpuinfo
65. how to see list of storage devices, disk partition --> lsblk
66. See OS name of linux server --> uname -a && cat /etc/os-release
## Process Management
67. Check if a process is running or not --> ps -ef | grep chrony
68. How to get a PID of process --> pgrep chron
69. Stop a process by PID --> kill -9 PID (-9 using for forcefully)
70. Stop a process by its name --> pkill httpd
71. How to see all the active jobs --> jobs
72. Resume a job in background --> bg
73. Resume a job in foreground --> fg
74. Run a script in background --> nohup ./script >/dev/null &
## Network INFO
75. How to check the IP of machine --> ifconfig
76. Check if a IP:Port is accessible and open or not --> telnet IP Port
77. Check if port is open or not on our server --> netstat -putan | grep 80
78. Check all hubs in network path to reach a website --> traceroute <url/IP>
## User Creation
79. Create a new user --> useradd <usernam> && id <username>
80. Change password for the user --> passwd <username>
81. Switch to the different user --> su <user_name>
82. Create a new group --> groupadd <group_name> && cat /etc/group
83. Check userId or groupId of the user --> id <user_name>
84. Delete a user or group
userdel <user_name>
groupdel <group_name>
85. How to add a user in different group --> sudo usermod -G <Group_name> <user_name>
86. Schedule a script to run on a particular date/time --> at, crontab
at is use for running or perform some task only once 
For example:
Check time using date command: date
at 05:30 PM
Then will get the prompt so just give:
echo "at command example" > at_demo.txt
Then Press ctrl + d
87. Insert the data --> ls > demo.txt.
88. Append the data means without deleting the content of file --> ls >> demo.txt

89. Find iNode for a file ==> ls -li
inode is an index node. It serves as a unique identifier for a specific piece of metadata on a given filesystem.

90. Use of shred command (permanently delete a file which is unable to recover) ==>
shred -u file_name
shred --remove file_name {for overwriting and delete}
91. Combine two files ==> cat file1 file2 > file3
92. Find the type of file ==> file <file_name>
93. Redirect an error of command into a file ==> 2>
94. Redirect both error and output of command into a file ==> 2>&1

## Cron Job
95. Meaning of the cron job (* * * * *) ==> 'minute' 'hour' 'day of month' 'month' 'day of week'   (0-59) (0-23) (1-31) (1-12) (0-6)
96. If your cron job didn't work, how would you check ==>
check system time,
crontab entry,
check /var/log/messages

## Services
97. Service that keep running in the background like httpd, chronyd, sshd ==>  Daemon service
98. What is Process ?
== Process is a instance of running program
== When you start a program application or execute a command, a process is created
== For every process unique no. is assigned which is called PID (Process ID)
99. Get info about ports ==> netstat -tln
100. Check Network interfaces in Linux ==> netstat -i and ifconfig
101. What is kernel ?
Linux Kernel is the main component of Linux oS and is the core interface b/w a computer h/w and its processes.
102. What is Swap Space ??
Swap space in Linux is used when the amount of physical memory (RAM) is full. If the system needs more memory resources and the RAM is full, inactive pages in memory are moved to swap space.

80/tcp                                   # ======> HTTP (Hypertext Transfer Protocol)
443/tcp                                  # ======> HTTPS (Hypertext Transfer Protocol Secure)
22/tcp                                   # ======> SSH (Secure Shell)
21/tcp                                   # ======> FTP (File Transfer Protocol)
25/tcp                                   # ======> SMTP (Simple Mail Transfer Protocol)
53/tcp                                   # ======> DNS (Domain Name System)
53/udp
123/udp                                  # ======> NTP (Network Time Protocol)
389/tcp                                  # ======> LDAP (Lightweight Directory Access Protocol)
389/udp
636/tcp                                  # ======> LDAPS (LDAP over SSL)
ufw allow 68/udp                         # ======> DHCP (Dynamic Host Configuration Protocol)
3128                                     # ======> squid
103. Command which send exactly 5 packets to google.com ==> ping -c 5 google.com
104. File contains a list of groups ==> /etc/group
105. Which of the following contains the value of exit status of the previously executed commmand ==> $?
106. Command should use to get the list of connected USB devices ==> 
listusb
usbls
lsusb 
getusb
107. What are the valid values of exit status ==> 0 - 255
108. Transfer file from Windows server to Linux server or vice-versa ==> Using SSH, FTP, SFTP and tools like WinSCP, FileZilla
109. What is tee command used for (gives the output on screen and insert in file) ==> ls | tee files.txt
110. xargs used for ==> It convert stnInput into command line argument
111. I wanna read only 26th to 30th line of file ==> head -30 file_name | tail -f
112. What is ACL and it's advantage
Ans.- Access Control List is used to modify the permissions of files and for this we use setfacl and getfacl cmds.
Advantage: we can provide permission to the specific user

113. Difference b'w softlink and hardlink
114. Ans.- Softlink: Link will be removed if original file is removed/deleted. (ln -s)
Hardlink: Renaming, deleting or removing the file will not effect the link. (ln)
115. Nice value of process ==> Niceness scale goes from -20 to 19. The lower the no. more priority that task gets.
Process priority = nice
ex.- nice -n 5 process
116. How to check the nice value of process ==> ps -l PID (For PID either can use ps or pid of service_name)
117. You want a process with a PID of 8675 to complete its task faster than the default rate ==> renice -20 -p 8675 (This can also be done by top command)
118. If you want your process keep running in background after closing the terminal ==> nohup
nohup process &
nohup process > /dev/null 2>&1 &
119. Display info about kernel related messages along with hardware ans system startup messages stored in kernel ring buffer ==> dmesg
120. Command to show all the lines except any lines starting with '#' in a file ==> cat file | grep -v ^#
121. What is hypervisor ==> It's a software that creates and runs VMs
122. Command to display a list of currently configured Physical volumes ==> sudo lvs (use 'vgs' for volume groups)
123. Filesystem ==> OS stores and manages the data or partitions using a structure called filesystem
Filesystem include files, directories and it's related permissions. FS stores data in hierarchy of directories and files
124. How to check your Linux Filesystem ==> lsblk -f

## SHELL 
125. Shell is a interface/command line for user. A shell provide an environment to a user to execute commands and interact with terminal.
126. Total shells available in your system ==> /etc/shells
127. How to check which shell you are in or running ==> echo $0 or echo $SHELL
128. Different type of shells ==> Bash, ZSH, KSH TcSH, FiSH etc
129. Change the shell ==> chsh
130. How to make any variable unchangeable or readonly ==> readonly variable_name=value
131. How to find out how many arguments passed to a script ==> using '$#'
132. $* ==> consider all the arguents as single entry
133. $@ ==> considers all the arguments as separate entry
Example- for i in "$@"
134. In what ways, shell script get input values from user or terminal
i.  By read command: read -p 'your name' name
ii. By parameters: ./script.sh params1 params2
135. How can we debug the shell script ==> set -x or set -v
136. What's the use of '$$' ==> $$ gives you the current process ID
137. What are loops in shell scripting and types
Ans.- Loops are used to repeatdly run a portion of script for a given no. of repetitions or until condition is met
i. for loop
ii. while loop
iii. until loop
139. How to define a infinite loop in shell scripting ==> while true or while :
140. How to use expressions in script ==> let
Ex.- let i++
141. How to get the name of current script and print within a script
Ans.- we can use ${0} within a script which will print the name of current running script.
142. How to make a basic function in shell scripting
function myfun {
 echo "Hello World!"
}
myfun() {}
144. How to print a random integer in shell scripting ==> we can use builtin bash variable called 'RANDOM'
which will print random no. between 0-32767
145. In a shell script, what will you do if you don't want to print the output of a command on terminal or in a file
Ans.- we can redirect the output to /dev/null
146. What's the use of logger in shell scripting ==>
It is used to maintain the logs for your script
we can find the logs under /var/logs/messages
147. What is the use of exit status $? in a shell scripting ?
.....
# ======================== END ========================
