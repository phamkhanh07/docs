# Basic Linux
## Cài đặt HĐH
### ubuntu
### Cent
### Suse
### partitioning
    fdisk
### bootloader
### base packages
### RAID
### format cài SuSE
## Tools and basic commands
### Basic commands

`pwd` - gives us the absolute path  
`ls` - list file in directory  
`cd` - go to a directory  
`mkdir` - create a folder  
`rmdir` - delete a directory  
`rm` - delete files and directories  
`touch` - create a file  
`man` and `--help` - To know more about a command and how to use it  
`cp` - copy files through the command line  
`mv` - move files through the command line  
`locate` - locate a file in a Linux system  
`echo` - move some data, usually text into a file  
`cat` - display the contents of a file  
`vi` - vim   
`sudo` - stands for "SuperUser Do"  
`df` - See the available disk space in each of the partitions in your system  
`du` - disk usage of a file in your system  
`tar` - tar to work with tarballs (or files compressed in a tarball archive) in the Linux command line  
`uname` - Use uname to show the information about the system your Linux distro is running  
`chmod` - change the permissions granted to it in Linux  
`hostname` - know your name in your host or network  
`whoami` - know who am i
`ping` 
`ifconfig` and `ip r` - show ip of server linux
`tail`- displays the last part of a file
`grep` - searches file patterns
`wget` - retrieving files using HTTP, HTTPS, FTP and FTPS
### Tools
`curl` - transfers data to or from a network server, using one of the supported protocols (HTTP, HTTPS, FTP, FTPS, SCP, SFTP, TFTP, DICT, TELNET, LDAP or FILE)  
`htop` - show proscess and performance in server  
`tcpdump` - used capture or filter TCP/IP packets that received or transferred on a specific interface over a network  
`netstat` `netstat- nltp` - show port opend  
`nmon` - monitoring  
`nmap` - utility for network discovery
## filesystem layout
    /bin - Binaries.
    /boot - Files required for booting.
    /dev - Device files.
    /etc - Et cetera. The name is inherited from the earliest Unixes, which is when it became the spot to put config-files.
    /home - Where home directories are kept.
    /lib - Where code libraries are kept.
    /media - A more modern directory, but where removable media gets mounted.
    /mnt - Where temporary file-systems are mounted.
    /opt - Where optional add-on software is installed. This is discrete from /usr/local/ for reasons I'll get to later.
    /run - Where runtime variable data is kept.
    /sbin - Where super-binaries are stored. These usually only work with root.
    /srv - Stands for "serve". This directory is intended for static files that are served out. /srv/http would be for static websites, /srv/ftp for an FTP server.
    /tmp - Where temporary files may be stored.
    /usr - Another directory inherited from the Unixes of old, it stands for "UNIX System Resources". It does not stand for "user" (see the Debian Wiki). This directory should be sharable between hosts, and can be NFS mounted to multiple hosts safely. It can be mounted read-only safely.
    /var - Another directory inherited from the Unixes of old, it stands for "variable". This is where system data that varies may be stored. Such things as spool and cache directories may be located here. If a program needs to write to the local file-system and isn't serving that data to someone directly, it'll go here.

## unix permission
![file permission](./file_permissions.png)
 The Permission Groups used are:
- u – Owner: the owner's permissions determine what actions the owner of the file can perform on the file
- g – Group: the group's permissions determine what actions a user, who is a member of the group that a file belongs to, can perform on the file.   
- o – Others: the permissions for others indicate what action all other users can perform on the file.
- a – All users include u, g, o
The Permission Types that are used are:
- r – Read
- w – Write
- x – Execute

Changing Permissions  
\+ Adds the designated permission(s) to a file or directory.  
\- Removes the designated permission(s) from a file or directory.   
\= Sets the designated permission(s).  
root, has the unlimited capability to modify the ownership of any file but normal users can change the ownership of only those files that they own.  
Using `chmod` to change file permissions: The symbolic method and the absolute form

Symbolic method:
- `chmod a-rw file1`  
all remove read and write privilege designated from file1
- `chmod ug+rw file1`  
u and g add read and wirte to file1 

Absolute form:
| Permission |  Number |
|------------|--------|
| Read (r)   |	4 |
| Write (w)  | 	2 |
| Execute (x) |	1 |

Example:  
For file **file1**, to grant read, write, and execute permissions to yourself (4+2+1=7), read and execute permissions to users in your group (4+0+1=5), and only execute permission to others (0+0+1=1).  
user command:  
`chmod 751 file1`  
To grant read, write, and execute permissions on the current directory to yourself only.  
`chmod 700`

## Vim commands
Cursor movement

    h - move left
    j - move down
    k - move up
    l - move right
    w - jump by start of words (punctuation considered words)
    W - jump by words (spaces separate words)
    e - jump to end of words (punctuation considered words)
    E - jump to end of words (no punctuation)
    b - jump backward by words (punctuation considered words)
    B - jump backward by words (no punctuation)
    0 - (zero) start of line
    ^ - first non-blank character of line
    $ - end of line
    G - Go To command (prefix with number - 5G goes to line 5)

Note: Prefix a cursor movement command with a number to repeat it. For example, 4j moves down 4 lines.
Insert Mode - Inserting/Appending text

    i - start insert mode at cursor
    I - insert at the beginning of the line
    a - append after the cursor
    A - append at the end of the line
    o - open (append) blank line below current line (no need to press return)
    O - open blank line above current line
    ea - append at end of word
    Esc - exit insert mode

Editing

    r - replace a single character (does not use insert mode)
    J - join line below to the current one
    cc - change (replace) an entire line
    cw - change (replace) to the end of word
    c$ - change (replace) to the end of line
    s - delete character at cursor and subsitute text
    S - delete line at cursor and substitute text (same as cc)
    xp - transpose two letters (delete and paste, technically)
    u - undo
    . - repeat last command

Marking text (visual mode)

    v - start visual mode, mark lines, then do command (such as y-yank)
    V - start Linewise visual mode
    o - move to other end of marked area
    Ctrl+v - start visual block mode
    O - move to Other corner of block
    aw - mark a word
    ab - a () block (with braces)
    aB - a {} block (with brackets)
    ib - inner () block
    iB - inner {} block
    Esc - exit visual mode

Visual commands

    > - shift right
    < - shift left
    y - yank (copy) marked text
    d - delete marked text
    ~ - switch case

Cut and Paste

    yy - yank (copy) a line
    2yy - yank 2 lines
    yw - yank word
    y$ - yank to end of line
    p - put (paste) the clipboard after cursor
    P - put (paste) before cursor
    dd - delete (cut) a line
    dw - delete (cut) the current word
    x - delete (cut) current character

Exiting

    :w - write (save) the file, but don't exit
    :wq - write (save) and quit
    :q - quit (fails if anything has changed)
    :q! - quit and throw away changes

Search/Replace

    /pattern - search for pattern
    ?pattern - search backward for pattern
    n - repeat search in same direction
    N - repeat search in opposite direction
    :%s/old/new/g - replace all old with new throughout file
    :%s/old/new/gc - replace all old with new throughout file with confirmations

Working with multiple files

    :e filename - Edit a file in a new buffer
    :bnext (or :bn) - go to next buffer
    :bprev (of :bp) - go to previous buffer
    :bd - delete a buffer (close a file)
    :sp filename - Open a file in a new buffer and split window
    ctrl+ws - Split windows
    ctrl+ww - switch between windows
    ctrl+wq - Quit a window
    ctrl+wv - Split windows vertically
## SSH 
`ssh` - use to ssh to server `ssh user_name@host(IP/Domain_name)`  
`ssh-keygen` - creates a key pair for public key authentication  
`ssh-copy-id` - configures a public key as authorized on a server  
`ssh-agent` - agent to hold private key for single sign-on  
`ssh-add` - tool to add a key to the agent  
`scp` - file transfer client with RCP-like command interface  
`sftp` - file transfer client with FTP-like command interface  
    user command from sftp server to client add l: ex: llcd, lls..
`sshd` - OpenSSH server  

## services managements
### systemctl
Control the systemd system and service manager
```
# systemctl start sshd
# systemctl stop sshd.service
# systemctl enable sshd.service
# systemctl disable sshd.service
```

### sysvinit
System V (Sys V) is one of the first and traditional init systems for the UNIX/Linux operating system. Init is the first process started by the kernel during system boot, and is a parent process for everything.  
Most Linux distributions first started using the traditional init system, called System V (Sys V).

### systemd
systemd is a new init system and system manager that has become so popular that it has been widely transformed into the new standard init system by most Linux distributions.
Systemctl is a systemd application that allows you to manage the systemd system.
### Service Commands

Short Description | 	SysVinit Command | 	systemd Command 
-------------------|--------------------|------------------
To Start a Service |	service example start |	systemctl start example
To Stop a Service  |    service example stop |	systemctl stop example
Restart a Service  | 	service example restart| 	systemctl restart example
Reload a Service   |	service example reload 	|systemctl reload example
Restarts if the service is already running | service example condrestart |	systemctl condrestart example
How to check if a service is currently running | service example status |systemctl status example
How to enable a service on boot/startup | 	chkconfig example on |	systemctl enable example
How to disable a service on boot/startup |	chkconfig example off |	systemctl disable example
How to check if a service is configured to start on boot or not | 	chkconfig example –list |	systemctl is-enabled example
How to display a list of enabled or disabled services on boot with runlevels information |	chkconfig |	systemctl list-unit-files –type=service
Create a new service file or modify any configuration |	chkconfig example –add 	|systemctl daemon-reload

### Runlevels/Targets

Short Description 	| SysVinit Command |	systemd Command
--------------------|------------------|------------------
To halt the system |	0, halt |	runlevel0.target, poweroff.target, systemctl halt
Single user mode |	1, S, single |	runlevel1.target, rescue.target
Multi User 	|2 |	runlevel2.target, multi-user.target
Multi User with Network |	3 |	runlevel3.target, multi-user.target
Experimental (No User) |	4 |	runlevel4.target, multi-user.target
Multi-user with Graphical & Network |	5 |	runlevel5.target, graphical.target
To reboot a system |	6, reboot |	runlevel6.target, reboot.target, systemctl reboot
Emergency shell |	emergency |	emergency.target

### Other systemd Commands
Short Description |	systemd Command
------------------|----------------
Control the system hostname |	hostnamectl
Team daemon control tool |	teamdctl
Control the system time and date |	timedatectl
Query the systemd journal |	journalctl
How to check system boot time |	systemd-analyze or systemd-analyze time
How to check each service time consumption at startup |	systemd-analyze blame
Kill all processes associated with a service |	systemctl kill example
List all running services |	systemctl
Show system status |	systemctl status
How to run the systemd command on a remote machine |	systemctl status example -H user@remotehost

## system logs
Common Linux log files names and usage

    /var/log/messages : General message and system related stuff
    /var/log/auth.log : Authentication logs
    /var/log/kern.log : Kernel logs
    /var/log/cron.log : Crond logs (cron job)
    /var/log/maillog : Mail server logs
    /var/log/qmail/ : Qmail log directory (more files inside this directory)
    /var/log/httpd/ : Apache access and error logs directory
    /var/log/lighttpd/ : Lighttpd access and error logs directory
    /var/log/boot.log : System boot log
    /var/log/mysqld.log : MySQL database server log file
    /var/log/secure or /var/log/auth.log : Authentication log
    /var/log/utmp or /var/log/wtmp : Login records file
    /var/log/yum.log : Yum command log file.

rsyslogd  
logs are generated using rsyslogd service. rsyslog config in  

    /etc/rsyslog.conf  
    /etc/rsyslog.d/

## Package manager
DPKG – Debian Package Management System
RPM – Red Hat Package Manager
APT - Advanced Packaging Tool
RPM - Red Hat Package Manager
YUM - Yellowdog Updater, Modified
Zypper - Package Manager openSUSE
## firewall and iptables
iptables  

    Iptables là giao diện dòng lệnh để tương tác với tính năng packet filtering của netfilter framework.
    Cơ chế packet filtering của iptables hoạt động bao gồm 3 thành phần sau: tables, chains và targets.
Các table trong iptables
    Table filter
    Table NAT
    Table mangle
    Table raw
    Table security

## time sync with NTP services/ client

# services thông dụng
## web server 
## file server
## database server
## mail server
## DNS server
## DHCP server
# Chủ đề nâng cao
## filesystem formats
## scripting
## building software
## TCP/HTTP service load balancing
    1. haproxy
    2. keepalive + EIP
    3. lsync
## Web server tunning
    1. Một số tham số trong config của Apache/NGINX/FPM/PHP
    2. Process model
    3. Kiểm soát về bảo mật:
    - chroot
    - open_basedir
    - function blacklist
    - request filtering
    - Compression
    - Control headers
## HTTP cache sử dụng NGINX

## SSL offloading
    1. Haproxy
    2. nginx
## Basic database tuning
## Iptables/ SuSEfirewall2
## System limit / kernel tunning / TCP parameters
## LVM
## Software RAID using md
## Data encryption: GPG
## System encryption: Truecrypt/ LUKS
## Database cluster
## IP tunneling/ virtual network
    1. GRE
    2. vxlan
    3. ssh tunnel
    4. ipip
    5. L2TP/VPN


## DDOS optimized firewall
    1. SYNProsxy
    2. iptables with ipset + GeoIP control
    3. TCP tunning
## Các control panel thương mại phổ biến
## System monitoring
    1. Hardware health monitor (OS level): RAM; HDD; RAID controller
    2. logwatch
    3. rrd stats collect
    4. netdata



