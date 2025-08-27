# Linux Commands Cheatsheet for DevOps

This is a **comprehensive Linux commands guide for DevOps engineers**, covering essential commands with **syntax, explanation, and examples**.

---

## 📂 1. File & Directory Management

### `ls` – List directory contents

**Syntax:**

```bash
ls [options] [directory]
```

**Examples:**

```bash
ls -l /var/log     # Long listing with details
ls -a              # Show hidden files
ls -lh             # Human-readable file sizes
```

---

### `pwd` – Print working directory

**Syntax:**

```bash
pwd
```

**Example:**

```bash
pwd   # Output: /home/devuser/projects
```

---

### `cd` – Change directory

**Syntax:**

```bash
cd [path]
```

**Examples:**

```bash
cd /etc        # Go to /etc
cd ..          # One level up
cd ~           # Go to home directory
```

---

### `mkdir` – Create directories

**Syntax:**

```bash
mkdir [options] directory_name
```

**Examples:**

```bash
mkdir test
mkdir -p dir1/dir2/dir3   # Create nested directories
```

---

### `touch` – Create empty file / update timestamp

**Syntax:**

```bash
touch filename
```

**Examples:**

```bash
touch file.txt
touch {file1,file2}.log   # Create multiple files
```

---

### `cp` – Copy files/directories

**Syntax:**

```bash
cp [options] source destination
```

**Examples:**

```bash
cp file1.txt file2.txt    # Copy file
cp -r dir1 dir2           # Copy directory recursively
```

---

### `mv` – Move/Rename files

**Syntax:**

```bash
mv source destination
```

**Examples:**

```bash
mv file.txt newname.txt   # Rename
mv file.txt /tmp/         # Move to /tmp
```

---

### `rm` – Remove files/directories

**Syntax:**

```bash
rm [options] file
```

**Examples:**

```bash
rm file.txt       # Delete file
rm -r folder/     # Delete folder recursively
rm -i file.txt    # Prompt before deleting
```

---

### `find` – Search for files

**Syntax:**

```bash
find [path] [options] [expression]
```

**Examples:**

```bash
find /var/log -name "*.log"    # Find log files
find . -type f -size +10M      # Files bigger than 10MB
```

---

## 📖 2. File Viewing & Text Processing

### `cat` – View file contents

**Syntax:**

```bash
cat [file...]
```

**Examples:**

```bash
cat file.txt
cat file1 file2 > merged.txt   # Merge files
```

---

### `echo` – Print text to screen/file

**Syntax:**

```bash
echo [options] "text"
```

**Examples:**

```bash
echo "Hello DevOps"
echo "export PATH=$PATH:/opt/bin" >> ~/.bashrc
```

---

### `head` – Show first lines of a file

**Syntax:**

```bash
head [options] file
```

**Examples:**

```bash
head file.txt
head -n 20 file.txt   # Show first 20 lines
```

---

### `tail` – Show last lines of a file

**Syntax:**

```bash
tail [options] file
```

**Examples:**

```bash
tail file.txt
tail -f /var/log/syslog   # Follow log in real-time
```

---

### `less` – Scrollable file viewer

**Syntax:**

```bash
less file
```

**Example:**

```bash
less bigfile.log
```

---

### `more` – Simple file pager

**Syntax:**

```bash
more file
```

**Example:**

```bash
more notes.txt
```

---

### `wc` – Count words/lines/bytes

**Syntax:**

```bash
wc [options] file
```

**Examples:**

```bash
wc -l file.txt   # Count lines
wc -w file.txt   # Count words
wc -c file.txt   # Count bytes
```

---

### `sort` – Sort lines in a file

**Syntax:**

```bash
sort [options] file
```

**Examples:**

```bash
sort names.txt
sort -r numbers.txt   # Reverse sort
sort -n numbers.txt   # Numeric sort
```

---

### `diff` – Compare two files

**Syntax:**

```bash
diff file1 file2
```

**Examples:**

```bash
diff config.old config.new
```

---

### `cut` – Extract columns from text

**Syntax:**

```bash
cut [options] file
```

**Examples:**

```bash
cut -d":" -f1 /etc/passwd   # Extract usernames
```

---

### `tee` – Output to screen + file

**Syntax:**

```bash
command | tee [options] file
```

**Examples:**

```bash
ls -l | tee list.txt
```

---

## ⚙️ 3. Process Management

### `ps` – View running processes

**Syntax:**

```bash
ps [options]
```

**Examples:**

```bash
ps aux           # Detailed view of all processes
ps -ef           # Full format
```

---

### `top` – Real-time process monitoring

**Syntax:**

```bash
top
```

**Examples:**

```bash
top
htop   # (better alternative if installed)
```

---

### `kill` – Terminate a process

**Syntax:**

```bash
kill [options] PID
```

**Examples:**

```bash
kill 1234         # Kill by PID
kill -9 1234      # Force kill
```

---

### `fuser` – Show which process uses a file/port

**Syntax:**

```bash
fuser [options] file
```

**Examples:**

```bash
fuser -v /var/log/syslog
fuser -k 8080/tcp   # Kill process on port 8080
```

---

### `nohup` – Run command immune to hangups

**Syntax:**

```bash
nohup command &
```

**Examples:**

```bash
nohup python3 app.py &
```

---

### `uptime` – Show system uptime

**Syntax:**

```bash
uptime
```

**Example:**

```bash
uptime
```

---

## 🖥️ 4. System Info & Monitoring

### `df` – Disk usage

**Syntax:**

```bash
df [options]
```

**Examples:**

```bash
df -h        # Human readable
```

### `du` – Directory size

**Syntax:**

```bash
du [options] [path]
```

**Examples:**

```bash
du -sh *     # Summary per folder
```

### `free` – Memory usage

**Syntax:**

```bash
free [options]
```

**Examples:**

```bash
free -h      # Human readable
```

### `vmstat` – System performance

**Syntax:**

```bash
vmstat [options]
```

**Examples:**

```bash
vmstat 5     # Update every 5 sec
```

### `uname` – System info

**Syntax:**

```bash
uname [options]
```

**Examples:**

```bash
uname -a
```

---

## 👤 5. User & Permission Management

### `who` – Logged in users

**Syntax:**

```bash
who
```

### `whoami` – Current user

**Syntax:**

```bash
whoami
```

### `id` – User identity

**Syntax:**

```bash
id
```

### `useradd` – Add new user

**Syntax:**

```bash
useradd [options] username
```

**Example:**

```bash
sudo useradd devuser
```

### `passwd` – Set/change password

**Syntax:**

```bash
passwd username
```

### `su` – Switch user

**Syntax:**

```bash
su [username]
```

### `exit` – Logout shell

**Syntax:**

```bash
exit
```

### `userdel` – Delete user

**Syntax:**

```bash
userdel [options] username
```

### `groupadd` – Add new group

**Syntax:**

```bash
groupadd groupname
```

### `gpasswd` – Set group password

**Syntax:**

```bash
gpasswd groupname
```

### `groupdel` – Delete group

**Syntax:**

```bash
groupdel groupname
```

### `chmod` – Change file permissions

**Syntax:**

```bash
chmod [mode] file
```

**Examples:**

```bash
chmod 755 script.sh
chmod u+x file.sh
```

### `umask` – Default permission mask

**Syntax:**

```bash
umask [value]
```

### `chown` – Change file owner

**Syntax:**

```bash
chown owner file
```

### `chgrp` – Change group ownership

**Syntax:**

```bash
chgrp group file
```

### `sudo` – Run command as root

**Syntax:**

```bash
sudo command
```

---

## 📦 6. Archiving & Compression

### `tar` – Archive files

**Syntax:**

```bash
tar [options] archive.tar files
```

**Examples:**

```bash
tar -cvf backup.tar /home/user
tar -xvf backup.tar
```

### `gzip` / `gunzip` – Compress/uncompress

```bash
gzip file
gunzip file.gz
```

### `zip` / `unzip` – Zip archive

```bash
zip archive.zip file1 file2
unzip archive.zip
```

---

## 🌐 7. Networking & Security

### `ping` – Test connectivity

```bash
ping hostname
```

### `ssh` – Secure shell

```bash
ssh user@host
```

### `scp` – Secure copy

```bash
scp file user@host:/path/
```

### `rsync` – Sync files

```bash
rsync -av file user@host:/path/
```

### `ssh-copy-id` – Copy SSH keys

```bash
ssh-copy-id user@host
```

### `netstat` – Network connections

```bash
netstat -tulnp
```

### `ss` – Socket stats

```bash
ss -tulnp
```

### `ifconfig` – Network interfaces

```bash
ifconfig
```

### `ip` – Modern replacement

```bash
ip address show
ip route show
```

### `traceroute` – Trace hops

```bash
traceroute host
```

### `tracepath` – Trace hops (no root needed)

```bash
tracepath host
```

### `mtr` – Traceroute + ping

```bash
mtr host
```

### `nslookup` – DNS lookup

```bash
nslookup google.com
```

### `dig` – Advanced DNS query

```bash
dig google.com
```

### `whois` – Domain info

```bash
whois google.com
```

### `telnet` – Connect to host/port

```bash
telnet host port
```

### `curl` – Fetch URLs

```bash
curl -I https://example.com
```

### `wget` – Download files

```bash
wget https://example.com/file.zip
```

### `iptables` – Firewall rules

```bash
iptables -L
```

### `nmap` – Network scanner

```bash
nmap host
```

### `arp` – Show ARP table

```bash
arp -a
```

### `hostname` – Show/set hostname

```bash
hostname
```

### `nc` (netcat) – Debug connections

```bash
nc -zv host 22
```

---

## 📦 8. Package Management (Debian/Ubuntu)

### `apt update` – Update repo index

```bash
sudo apt update
```

### `apt upgrade` – Upgrade packages

```bash
sudo apt upgrade
```

### `apt install` – Install package

```bash
sudo apt install nginx
```

### `apt remove` – Remove package

```bash
sudo apt remove nginx
```

### `apt search` – Search packages

```bash
apt search docker
```

---

## 🔌 9. System Control

### `shutdown` – Power off

```bash
sudo shutdown -h now
```

### `reboot` – Restart system

```bash
sudo reboot
```

### `date` – Show/set date

```bash
date
date +"%Y-%m-%d %H:%M:%S"
```

### `clear` – Clear terminal

```bash
clear
```

### `watch` – Repeat command

```bash
watch -n 5 df -h
```

---

# ✅ Final Notes

* These commands are **core to Linux administration in DevOps**.
* Mastering them helps in **CI/CD pipelines, automation, server management, and troubleshooting**.

---