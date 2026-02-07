
Here is a condensed cheat sheet for **Working with Shell 1**, organized for quick reference.

### **Navigation & Directory Basics**

| **Command**   | **Description**                            | **Example**    |
| ------------- | ------------------------------------------ | -------------- |
| **`pwd`**     | Print Working Directory (Where am I?).     | `pwd`          |
| **`ls`**      | List files in current folder.              | `ls`           |
| **`ls -l`**   | Long listing (permissions, size, etc.).    | `ls -l`        |
| **`ls -a`**   | List all (including hidden `.` files).     | `ls -a`        |
| **`ls -ltr`** | List by time, reversed (newest at bottom). | `ls -ltr`      |
| **`cd`**      | Change Directory.                          | `cd Documents` |
| **`cd ..`**   | Go up one level.                           | `cd ..`        |
| **`cd ~`**    | Go to home directory.                      | `cd ~`         |
| **`cd -`**    | Go to previous directory.                  | `cd -`         |

### **File & Directory Management**

| **Command**    | **Description**                       | **Example**          |
| -------------- | ------------------------------------- | -------------------- |
| **`mkdir`**    | Make a new directory.                 | `mkdir Photos`       |
| **`mkdir -p`** | Make parent directories as needed.    | `mkdir -p a/b/c`     |
| **`cp`**       | <br>a file.                           | `cp file1 file2`     |
| **`cp -r`**    | Copy a directory recursively.         | `cp -r dir1 dir2`    |
| **`mv`**       | Move or Rename a file/directory.      | `mv old.txt new.txt` |
| **`rm`**       | Remove (delete) a file.               | `rm file.txt`        |
| **`rm -r`**    | Remove a directory and contents.      | `rm -r foldername`   |
| **`touch`**    | Create empty file / Update timestamp. | `touch notes.txt`    |

### **Viewing Content**

| **Command**   | **Description**                     | **Example**          |
| ------------- | ----------------------------------- | -------------------- |
| **`cat`**     | Dump entire file content to screen. | `cat file.txt`       |
| **`less`**    | Scroll through file (q to quit).    | `less hugefile.log`  |
| **`head`**    | Show first 10 lines.                | `head file.txt`      |
| **`tail`**    | Show last 10 lines.                 | `tail file.txt`      |
| **`tail -f`** | Follow file changes live.           | `tail -f server.log` |

### **System & Hardware Info**

| **Command**           | **Description**                                                        | **Example**                                 |
| --------------------- | ---------------------------------------------------------------------- | ------------------------------------------- |
| **`dmesg`**           | Print kernel & boot messages.                                          | `dmesg \| less`                             |
| **`dmesg \| grep`**   | Filter kernel logs for specific hardware.                              | `dmesg \| grep usb`                         |
| **`udevadm monitor`** | Monitor hardware events in real-time.                                  | `udevadm monitor`                           |
| **`udevadm info`**    | Query detailed info about a device.                                    | `udevadm info --query=path --name=/dev/sda` |
| **Example**           |                                                                        |                                             |
| **`dmesg`**           | **Past/Logs:** Print kernel & boot messages.                           | `dmesg \| less`                             |
| **`udevadm`**         | **Present/Management:** Monitor real-time hardware events.             | `udevadm monitor`                           |
| **`lsblk`**           | **Storage:** List block devices (disks & partitions) in a tree view.   | `lsblk`                                     |
| **`lscpu`**           | **Processor:** Show CPU architecture (cores, threads, cache).          | `lscpu`                                     |
| **`lsmem`**           | **Memory:** List system memory blocks (RAM status).                    | `lsmem --summary`                           |
| **`lspci`**           | **Internal Devices:** List devices on the PCI bus (GPU, Network Card). | `lspci`                                     |
| **`lshw`**            | **Complete Inventory:** detailed info on ALL hardware (requires root). | `sudo lshw -short`                          |

---

### **Quick Tip: The `ls` Family**

A good way to remember these is that they all start with `ls` (list):

- **`blk`** = **Bl**oc**k** devices (Storage)
    
- **`cpu`** = **CPU**
    
- **`mem`** = **Mem**ory
    
- **`pci`** = **PCI** cards
    
- **`hw`** = **H**ard**w**are (Everything)
### **Shortcuts & Help**

- **`TAB`**: Auto-completes file or command names (Press it often!).
    
- **`history`**: Shows list of past commands.
    
- **`man [command]`**: Opens the manual for a command.
    
- **`clear`**: Clears the terminal screen.
    
### **User Management**

| **Command**   | **Description**                  | **Example**              |
| ------------- | -------------------------------- | ------------------------ |
| **`useradd`** | Create a new user.               | `useradd mark`           |
| **`usermod`** | Modify an existing user.         | `usermod -aG group user` |
| **`userdel`** | Delete a user.                   | `userdel -r mark`        |
| **`passwd`**  | Set or change a user's password. | `passwd mark`            |


### **User & Group Management**

| **Command**    | **Description**                     | **Example**              |
| -------------- | ----------------------------------- | ------------------------ |
| **`useradd`**  | Create a new user.                  | `useradd mark`           |
| **`groupadd`** | Create a new group.                 | `groupadd developers`    |
| **`usermod`**  | Modify a user (e.g., add to group). | `usermod -aG group user` |
| **`userdel`**  | Delete a user.                      | `userdel -r mark`        |
| **`groupdel`** | Delete a group.                     | `groupdel developers`    |

---

### **Detailed Example Breakdown**

**1. Creating a User with Custom Options**

`useradd -u 1457 -d /var/www/mark -m mark`

- **`useradd`**: The command to create a new user account.
    
- **`-u 1457`**: Sets a specific **User ID (UID)** (instead of auto-assigning one).
    
- **`-d /var/www/mark`**: Sets a custom **Home Directory** location.
    
- **`-m`**: **Make** (create) the home directory folder if it doesn't exist.
    
- **`mark`**: The **Username**.
    

**2. Creating a Group**

`groupadd nautilus_sftp_users`

- **`groupadd`**: The command to create a new group.
    
- **`nautilus_sftp_users`**: The **Name** of the group.
    
    - _Why?_ This is often done to group specific users together (like SFTP users) so you can give them all the same permissions at once.
---

### **Detailed Example Breakdown**

**Command:**

`useradd -u 1457 -d /var/www/mark -m mark`

**What each part does:**

- **`useradd`**: The command to create a new user account.
    
- **`-u 1457`**: Sets a specific **User ID (UID)**.
    
    - _Why?_ Normally Linux assigns the next available number automatically. This forces the ID to be `1457`.
        
- **`-d /var/www/mark`**: Sets a custom **Home Directory**.
    
    - _Why?_ Default is `/home/mark`. This changes it to `/var/www/mark` (common for web developers).
        
- **`-m`**: **Make** the home directory.
    
    - _Why?_ Even if you specify a path with `-d`, Linux won't actually _create_ the folder unless you add this flag.
        
- **`mark`**: The **Username** of the account being created.

[root@stapp03 banner]# groupadd nautilus_sftp_users
[root@stapp03 banner]# useradd -m kano
[root@stapp03 banner]# usermod -aG nautilus_sftp_users kano

**Create Group $\rightarrow$ Create User $\rightarrow$ Add User to Group.**

### **Example Workflow: User & Group Setup**

**1. Create a Group**

`groupadd nautilus_sftp_users`

- **`groupadd`**: Creates a new group definition in the system.
    
- **`nautilus_sftp_users`**: The name of the group being created.
    

**2. Create a User**

`useradd -m kano`

- **`useradd`**: Creates the user account.
    
- **`-m`**: Ensures a home directory (usually `/home/kano`) is created for them.
    
- **`kano`**: The username.
    

**3. Add User to Group**

`usermod -aG nautilus_sftp_users kano`

- **`usermod`**: Modify an existing user account.
    
- **`-aG`**:
    
    - **`-a` (Append):** Adds the user to the group _without_ removing them from other groups. (Crucial! Without `-a`, they might lose their existing group memberships).
        
    - **`-G` (Groups):** Specifies that the next argument is the group name.
        
- **`nautilus_sftp_users`**: The group to join.
    
- **`kano`**: The user being modified.
    

---

### **Verification**

How do you check if it worked?

- **`id kano`**: Displays the user's ID and all groups they belong to.
    
    - _Output should look like:_ `uid=1001(kano) gid=1001(kano) groups=1001(kano),1002(nautilus_sftp_users)`


[root@stapp01 ~]# useradd -s /sbin/nologin anita

[root@stapp01 ~]# grep anita /etc/passwd
anita:x:1002:1002::/home/anita:/sbin/nologin

[root@stapp01 ~]# su - anita
This account is currently not available. 

The command sequence you pasted creates a user that **cannot log in**. This is a security feature, not an error.

### **What just happened?**

1. **`useradd -s /sbin/nologin anita`**: You created a user named `anita` but set her "shell" to be a special program called `/sbin/nologin`.
    
2. **`su - anita`**: When you tried to switch to this user, the system ran `/sbin/nologin` instead of a real shell (like bash).
    
3. **Result**: The `/sbin/nologin` program simply prints "This account is currently not available" and immediately kicks you out.
    

**Why do this?** This is used for **System/Service Accounts**. For example, a web server (Apache/Nginx) needs a user to "own" the web files for permissions, but no human should ever be able to log in as that web server user.

| **Command**      | **Description**                                 | **Example**                      |
| ---------------- | ----------------------------------------------- | -------------------------------- |
| **`useradd -s`** | Define the login shell (e.g., restrict access). | `useradd -s /sbin/nologin anita` |
| **`grep`**       | Check `/etc/passwd` to verify user details.     | `grep anita /etc/passwd`         |
### **Detailed Example Breakdown**

**Command:** `useradd -s /sbin/nologin anita`

- **`useradd`**: Create the user.
    
- **`-s` (Shell)**: Specifies which program runs immediately after login.
    
- **`/sbin/nologin`**: A "polite" fake shell that denies access and prints a message. (Another option is `/bin/false`, which denies access silently).
    
- **`anita`**: The username.
    

**Command:** `grep anita /etc/passwd`

- This confirms the setup. The output `anita:x:1002:1002::/home/anita:/sbin/nologin` shows the shell is successfully set to the last field.

### **Cheat Sheet: User Creation Options**

|**Command**|**Description**|**Example**|
|---|---|---|
|**`useradd -m`**|**Make** home directory (Standard).|`useradd -m kano`|
|**`useradd -M`**|**No** home directory (System/Service users).|`useradd -M javed`|
|**`useradd -s`**|Set login shell (e.g., `/bin/bash` or `/sbin/nologin`).|`useradd -s /bin/bash javed`|

---

### **Detailed Example Breakdown**

**1. Creating a User Without a Home Directory**

`useradd -M javed`

- **`-M`**: Tells Linux **NOT** to create the home directory folder on the hard drive.
    
- **Important Note:** Even though the folder wasn't created, Linux still assigns a _default path_ in the configuration.
    
    - _Evidence:_ `grep javed /etc/passwd` shows `/home/javed`.
        
    - _Reality:_ If you check `ls /home/javed`, you will see "No such file or directory."
        
    - _Consequence:_ If `javed` logs in, they will usually land in the root directory `/` or get a warning that their home directory is missing.
        

**2. The Error Message**

`su - jim` -> _user jim does not exist..._

- This simply means you tried to switch to a user (`jim`) that hasn't been created yet. You must run `useradd jim` first.
    

---

### **Summary of User Flags**

|**Flag**|**Memory Aid**|**Function**|
|---|---|---|
|**`-m`**|**M**ake it!|**Creates** the home folder physically.|
|**`-M`**|**M**issing!|**Does not create** the home folder.|
|**`-s`**|**S**hell|Sets the terminal program (bash, sh, nologin).|
|**`-u`**|**U**ID|Sets a specific ID number.|
|**`-d`**|**D**irectory|Sets a specific home path.|

|**Command**|**Description**|**Example**|
|---|---|---|
|**`useradd -e`**|Create user with an account expiry date.|`useradd -e 2027-01-28 siva`|
|**`chage`**|Change user password expiry info.|`chage -l siva`|
|**`chage -I`**|Set password inactivity period.|`chage -I -1 siva`|

---

### **Detailed Example Breakdown**

**1. Create User with Expiry Date**

`useradd -e 2027-01-28 siva`

- **`useradd`**: Create a new user.
    
- **`-e 2027-01-28`**: Sets the **Expiration Date** for the account (YYYY-MM-DD).
    
    - _Effect:_ On Jan 28, 2027, this account will automatically become locked and Siva won't be able to log in.
        
- **`siva`**: The username.
    

**2. Modify Password Aging**

`chage -I -1 siva`

- **`chage`**: (Change Age) Modifies password expiration policies.
    
- **`-I` (Capital i)**: Sets the **Inactivity** period (the grace period after a password expires).
    
- **`-1`**: This value means **"disable/never"**.
    
    - _Context:_ If this were set to `10`, the account would lock 10 days after the password expired if the user didn't change it. Setting it to `-1` removes that restriction.
        
- **`siva`**: The user being modified.
    

> **Note regarding your input `chage -1`:**
> 
> Standard Linux syntax is usually `chage -I -1` (capital i followed by negative one). If you typed literally `chage -1 siva` and it worked, it was likely interpreted as the Inactive flag, but strict syntax usually requires the `-I` flag first.

**Quick Check:** You can view all these settings for the user by running `chage -l siva` (list).

### **Advanced Search & Execute**

|**Command**|**Description**|**Example**|
|---|---|---|
|**`find`**|Search for files based on criteria.|`find /var -name "*.log"`|
|**`find -user`**|Search for files owned by a specific user.|`find /home -user kareem`|
|**`find -exec`**|Run a command on every file found.|`find ... -exec cp {} /backup \;`|
|**`cp --parents`**|Copy file **and** its full directory path.|`cp --parents dir/file.txt /dest`|
|**`wc -l`**|Count the number of lines (items) in the output.|`find ... \| wc -l`|

---

### **Detailed Example Breakdown**

**The Scenario:**

You found all files owned by `kareem` and copied them to `/news`, but you kept the folder structure intact.

**Command:**

`find /home/usersdata/ -type f -user kareem -exec cp --parents {} /news \;`

- **`find /home/usersdata/`**: Start searching inside this folder.
    
- **`-type f`**: Look for **Files** only (ignore directories).
    
- **`-user kareem`**: Filter results to only show files owned by **kareem**.
    
- **`-exec ... \;`**: For every single file found, **Execute** the following command.
    
- **`cp --parents`**: Copy the file, but **preserve the directory tree**.
    
    - _Without `--parents`:_ It would just copy `wp-config.php` to `/news/wp-config.php`.
        
    - _With `--parents`:_ It copies `/home/usersdata/wp-config.php` to `/news/home/usersdata/wp-config.php`. It automatically creates the folders inside `/news` so the file doesn't get "lost" or overwrite another file with the same name.
        
- **`{}`**: This is a placeholder. It effectively says "Insert the file you just found right here."
    
- **`/news`**: The destination folder.
    

**The Verification Command:**

`find ... | wc -l`

- **`|` (Pipe):** Takes the list of files found...
    
- **`wc -l`**: ...and counts the **l**ines. This tells you "1625 files matched."


### **Service Management (Systemd)**

|**Command**|**Description**|**Example**|
|---|---|---|
|**`systemctl start`**|Start a service immediately.|`systemctl start sshd`|
|**`systemctl stop`**|Stop a running service.|`systemctl stop sshd`|
|**`systemctl restart`**|Restart a service (stop then start).|`systemctl restart sshd`|
|**`systemctl enable`**|Start service automatically on boot.|`systemctl enable sshd`|
|**`systemctl status`**|Check if service is active/running.|`systemctl status sshd`|
|**`systemctl disable`**|Prevent service from starting on boot.|`systemctl disable sshd`|

### **SSH Security**

|**Command**|**Description**|**Example**|
|---|---|---|
|**`/etc/ssh/sshd_config`**|The main configuration file for SSH.|`vi /etc/ssh/sshd_config`|
|**`grep PermitRootLogin`**|Check current root login setting.|`grep PermitRootLogin /etc/ssh/sshd_config`|

---

### **Detailed Example Breakdown**

**The Scenario:**

You secured the server by disabling root login and then made sure the SSH service applied the changes and would start automatically next time the server reboots.

**1. Secure the Configuration**

`vi /etc/ssh/sshd_config`

- **Action:** You edited the file to find the line `PermitRootLogin` and changed it to `no`.
    
- **Why?** This prevents hackers from trying to brute-force the "root" password directly. They must log in as a normal user first, then switch to root, which is safer.
    

**2. Enable on Boot**

`systemctl enable sshd`

- **Action:** Creates a symbolic link so systemd knows to launch `sshd` when the computer turns on.
    
- **Output:** `Loaded: ... (; enabled; preset: enabled)` confirms this in your status output.
    

**3. Apply Changes**

`systemctl restart sshd`

- **Crucial Step:** Services do not see config file changes instantly. You **must** restart (or reload) the service for it to read the file again and apply your `PermitRootLogin no` rule.
    

**4. Verify Status**

`systemctl status sshd`

- **`Active: active (running)`**: This is the most important line. It means the service is healthy.
    
- **`since Thu 2026-02-05...`**: Tells you exactly when it started.
    
- **`Main PID: 2184`**: The Process ID. If the service hangs, you can `kill 2184` to force stop it.
    

> **Note on the error at the end:**
> 
> You saw `Failed to send unit change signal... Connection reset by peer`.
> 
> Since the status says `Active: active (running)`, the service **did** start correctly. This error often happens in lab environments (like Docker containers) where `systemd` doesn't have full communication permissions with the host. You can generally ignore it if the status is "Active".


### **Archiving & Compression (tar)**

|**Command**|**Description**|**Example**|
|---|---|---|
|**`tar -cvzf`**|**Create** a compressed archive (gzip).|`tar -cvzf archive.tar.gz /path/to/folder`|
|**`tar -xvzf`**|**Extract** a compressed archive.|`tar -xvzf archive.tar.gz`|
|**`tar -tf`**|**List** contents of an archive without extracting.|`tar -tf archive.tar.gz`|

---

### **Detailed Example Breakdown**

**Command:**

`tar -cvzf jim.tar.gz /data/jim`

- **`tar`**: Tape Archive utility (used for bundling files together).
    
- **`-c` (Create)**: Make a new archive.
    
- **`-v` (Verbose)**: Show the progress (list files as they are being added).
    
    - _Output:_ You saw the list of files (`nautilus2.txt`, etc.) because of this flag.
        
- **`-z` (Gzip)**: Compress the archive to save space (makes it a `.tar.gz` or `.tgz` file).
    
- **`-f` (File)**: Specify the filename of the archive (must be the last flag before the filename).
    
- **`jim.tar.gz`**: The name you want to give the new file.
    
- **`/data/jim`**: The source folder you are compressing.
    

### **The "Removing leading '/'" Warning**

You saw this message:

`tar: Removing leading '/' from member names`

- **Is it an error?** No, it is a safety feature.
    
- **What it means:** You asked to zip `/data/jim`. If `tar` kept the leading `/`, when someone unzips it later, it would try to force the files back into `/data/jim` on _their_ computer.
    
- **Why remove it?** By removing the `/`, the files become **relative**. If you move the zip file to `/home` and unzip it, the folder `jim` will appear inside `/home`, which is much safer and more flexible.

### **File Permissions (chmod)**

|**Command**|**Description**|**Example**|
|---|---|---|
|**`chmod +x`**|Make a file **eXecutable**.|`chmod +x script.sh`|
|**`chmod +r`**|Make a file **Readable**.|`chmod +r file.txt`|
|**`chmod +w`**|Make a file **Writable** (editable).|`chmod +w file.txt`|
|**`chmod 777`**|Give **ALL** permissions to everyone (Risky!).|`chmod 777 file.txt`|
|**`ls -l`**|View current permissions.|`ls -l script.sh`|

---
## 🔢 1. `chmod`: Changing Permissions
Permissions are calculated using Binary or Octal values. 
* **r (read)** = 4
* **w (write)** = 2
* **x (execute)** = 1

Permission Categories

A standard `chmod` command uses a three-digit octal number, where each digit corresponds to a specific user category in this order: 

- **First digit:** Permissions for the **owner** (user)
- **Second digit:** Permissions for the **group**
- **Third digit:** Permissions for **others** (everyone else)

### **Detailed Example Breakdown**

**Command:**

`sudo chmod +rx xfusioncorp.sh`

- **`sudo`**: Execute with root (admin) privileges. (Often needed for system scripts).
    
- **`chmod`**: **Ch**ange **Mod**e (the command to change permissions).
    
- **`+rx`**:
    
    - **`+`**: Adds permission (as opposed to `-` which removes it).
        
    - **`r` (Read)**: Allows the file to be opened and read.
        
    - **`x` (Execute)**: Allows the file to be run as a program.
        
- **`xfusioncorp.sh`**: The file name.
    

> **Important Note:**
> 
> As your notes mentioned, **scripts must be readable to be executable.** The shell needs to "read" the code inside the script to "run" it. That is why `+rx` is often used together.

---

### **Understanding `ls -l` Output**

When you run `ls -l`, you see something like `-rwxr-xr--`.

- **`-`**: First character is file type (`-` = file, `d` = directory).
    
- **`rwx`**: Owner permissions (Read, Write, Execute).
    
- **`r-x`**: Group permissions.
    
- **`r--`**: Everyone else's permissions.

Check files: `cd /tmp`

Change permissions: `sudo chmod +rx xfusioncorp.sh`

- `chmod`: The command used to change file permissions.
- `+rx`: The `+` sign grants the specified permissions, and `r` and `x` represent read and execute permissions, respectively. By using `+rx`, you are granting both read and execute permissions to the file.
- `file_name`: The name of the file you want to modify the permissions for.

Note: To make a file executable, it must also be readable.

Check the result: `ls -l xfusioncorp.sh`

Here is the **Access Control Lists (ACL)** section. This allows you to get much more specific than standard `chmod` permissions (e.g., giving permission to _just one specific user_ without changing the group owner).

### **Access Control Lists (ACL)**

|**Command**|**Description**|**Example**|
|---|---|---|
|**`getfacl`**|View the Access Control List of a file.|`getfacl file.txt`|
|**`setfacl -m`**|**m**odify permissions for a specific user/group.|`setfacl -m u:mark:rw file.txt`|
|**`setfacl -x`**|Remove a specific user/group rule.|`setfacl -x u:mark file.txt`|
|**`setfacl -b`**|**b**reak/remove **ALL** ACL entries (reset).|`setfacl -b file.txt`|

---

### **Detailed Example Breakdown**

**Command:**

`setfacl -m u:javed:-,u:eric:r /etc/resolv.conf`

_(Note: I added the second `u:` for clarity, though your syntax `u:javed:-,eric:r` is also valid shorthand)._

- **`setfacl`**: Set File Access Control List.
    
- **`-m`**: **Modify** existing rules (adds new ones or updates old ones).
    
- **`u:javed:-`**:
    
    - **`u`**: User.
        
    - **`javed`**: The specific username.
        
    - **`-`**: No permissions (Dash means "None"). Javed is effectively banned from this file.
        
- **`u:eric:r`**:
    
    - **`u`**: User.
        
    - **`eric`**: The specific username.
        
    - **`r`**: Read-only permission.
        
- **`/etc/resolv.conf`**: The file being modified.
    

**Understanding the Output:**

When you ran `getfacl` afterwards, you saw:

- `user::rw-`: The owner (root) still has Read/Write.
    
- `user:javed:---`: **Specific rule:** Javed has NOTHING.
    
- `user:eric:r--`: **Specific rule:** Eric has READ.
    
- `mask::r--`: This is the "ceiling" or maximum permission allowed for named users/groups.
    

---

### **Permissions vs. ACLs: The Difference**

- **`chmod` (Standard):** Can only set permissions for **One Owner**, **One Group**, and **Everyone Else**.
    
- **`setfacl` (ACL):** Can set permissions for **Infinite specific users**. (e.g., "Bob can read, Alice can write, Javed can do nothing, and everyone else can only read").

### **Text Processing (sed)**

|**Command**|**Description**|**Example**|
|---|---|---|
|**`sed`**|Stream Editor for filtering/modifying text.|`sed 's/snow/rain/g' file.txt`|
|**`sed -i`**|Edit the file **In-place** (save changes).|`sed -i 's/old/new/g' file.txt`|
|**`sed 's///g'`**|**S**ubstitute command with **G**lobal flag.|`sed 's/find/replace/g' file`|

---

### **Detailed Example Breakdown**

**Command:**

`sed -i 's#String#LUSV#g' /root/nautilus.xml`

- **`sed`**: The command (Stream Editor).
    
- **`-i` (In-place)**: This is crucial.
    
    - _Without `-i`:_ `sed` just shows you the preview of changes on the screen but leaves the file untouched.
        
    - _With `-i`:_ It actually **saves** the changes to the file.
        
- **`s` (Substitute)**: The action to perform (Find and Replace).
    
- **`#` (Delimiter)**:
    
    - Normally, people use slashes: `s/old/new/g`.
        
    - However, you can use **any** character as a separator (like `#`, `@`, or `|`).
        
    - _Why use `#`?_ It is very useful if your text contains slashes (like a URL or file path `/var/www`). If you used slashes as delimiters, you would have to "escape" the path slashes (e.g., `\/var\/www`), which looks messy. Using `#` makes it clean.
        
- **`String`**: The old text to look for.
    
- **`LUSV`**: The new text to replace it with.
    
- **`g` (Global)**:
    
    - _Without `g`:_ `sed` only replaces the _first_ match on each line.
        
    - _With `g`:_ `sed` replaces **all** matches on the line.


### **Detailed Breakdown**

**Command:**

`grep -e String /root/nautilus.xml | wc -l`

1. **`grep`**: The search tool (Global Regular Expression Print).
    
2. **`-e String`**: Specifies the **pattern** to search for.
    
    - _Note:_ You asked it to look for the exact text "String".
        
3. **`/root/nautilus.xml`**: The file being searched.
    
4. **`|` (Pipe)**: Takes the result of the search (the list of lines found) and passes it to the next command.
    
5. **`wc -l`**: Word Count with the **lines** flag.
    
    - Instead of printing the lines to the screen, it just counts them.
        

---

### **Interpreting Your Results**

- **Result `66`**:
    
    This means the word "String" was found on **66 lines** inside the file.
    
    _(If you just ran the `sed` command to replace "String" with "LUSV" and you still see 66, it means the replacement might not have worked, or there are still 66 instances left)._
    
- **Result `0`**:
    
    This means the word "About" was found **0 times**. It does not exist in the file.
    

---

### **Cheat Sheet Addition: Searching & Counting**

Here is the **Search (grep)** section for your cheat sheet.

|**Command**|**Description**|**Example**|
|---|---|---|
|**`grep`**|Search for text in a file.|`grep "error" log.txt`|
|**`grep -i`**|Search ignoring case (finds "Error", "ERROR").|`grep -i "error" log.txt`|
|**`grep -r`**|Recursive search (search inside all folders).|`grep -r "config" /etc/`|
|**`|wc -l`**|Count the number of matches found.|

### **Remote Transfer (scp)**

|**Command**|**Description**|**Example**|
|---|---|---|
|**`scp`**|**S**ecure **C**opy **P**rotocol (Copy files over SSH).|`scp file.txt user@server:/tmp`|
|**`scp -r`**|Recursive copy (for directories).|`scp -r /folder user@server:/tmp`|
|**`sudo su -`**|Switch to **Root** user with full environment.|`sudo su -`|

---

### **Detailed Example Breakdown**

**1. Switching Users**

`sudo su -`

- **`sudo`**: Run as superuser.
    
- **`su`**: Switch User.
    
- **`-` (Hyphen)**: This is important! It means "load the root user's environment variables (path, home dir, etc)." It simulates a fresh login as root.
    

**2. The "Garbage" Text**

`cat /tmp/nautilus.txt.gpg`

- **Output:** `T7/Xk8Rd=;l8...`
    
- **Why?** The file extension ends in **`.gpg`**. This stands for **GnuPG (Encryption)**.
    
- Because the file is encrypted, `cat` cannot read it as plain text. It displays raw binary data, which looks like random symbols on your screen. You would need to _decrypt_ it (using `gpg -d`) to read it.
    

**3. Transferring Files**

`scp -r /tmp/nautilus.txt.gpg tony@172.16.238.10:/tmp`

- **`scp`**: The command.
    
- **`-r`**: Recursive (used here just in case, though for a single file it's not strictly needed, but good habit).
    
- **`/tmp/nautilus.txt.gpg`**: The **Source** file (on your current computer).
    
- **`tony@172.16.238.10`**: The **Remote Destination**.
    
    - `tony`: The user you are logging into on the other computer.
        
    - `172.16.238.10`: The IP address of the other computer.
        
- **`:/tmp`**: The **Path** on the other computer where you want to drop the file.
    
    - _Note:_ The colon `:` separates the IP address from the directory path.

### **Cron Access Control**

|**File/Command**|**Description**|**Example**|
|---|---|---|
|**`/etc/cron.allow`**|**The VIP List:** Only users listed here can use cron.|`echo "rose" >> /etc/cron.allow`|
|**`/etc/cron.deny`**|**The Blacklist:** Users listed here cannot use cron.|`echo "ben" >> /etc/cron.deny`|
|**`crontab -e`**|Edit the current user's schedule.|`crontab -e`|
|**`>>`**|**Append** text to the end of a file.|`echo "user" >> file`|

---

### **Detailed Example Breakdown**

**1. allowing a user (`rose`)**

`echo "rose" >> /etc/cron.allow`

- **`echo "rose"`**: Takes the text "rose".
    
- **`>>`**: **Appends** it to the bottom of the file. (Important: If you used `>` with one arrow, it would erase the whole file and replace it with just "rose").
    
- **`/etc/cron.allow`**: This is the whitelist.
    
    - _Rule:_ If this file exists, **ONLY** people in this file can use cron. The system ignores `cron.deny`.
        

**2. Denying a user (`ben`)**

`echo "ben" >> /etc/cron.deny`

- **`/etc/cron.deny`**: This is the blacklist.
    
    - _Rule:_ If `cron.allow` does **NOT** exist, the system checks this file. Everyone can use cron **EXCEPT** the people listed here.
        

### **The Logic Hierarchy (The Bouncer Rule)**

1. **Does `cron.allow` exist?**
    
    - **YES:** Only let in users on the list. (Ignore `cron.deny`).
        
    - **NO:** Go to step 2.
        
2. **Does `cron.deny` exist?**
    
    - **YES:** Let everyone in **EXCEPT** users on the list.
        
    - **NO:** (Usually) Only Root can use cron.



### **System Targets (Runlevels)**

|**Command**|**Description**|**Example**|
|---|---|---|
|**`systemctl get-default`**|Check which mode the system boots into.|`systemctl get-default`|
|**`systemctl set-default`**|Change the boot mode (persistent).|`systemctl set-default graphical.target`|
|**`multi-user.target`**|**CLI Mode:** Text-only (Server standard).|_(Runlevel 3)_|
|**`graphical.target`**|**GUI Mode:** Windows/Desktop interface.|_(Runlevel 5)_|
|**`systemctl isolate`**|Switch mode **immediately** (without reboot).|`systemctl isolate multi-user.target`|
Here is the **System Targets (Runlevels)** section for your cheat sheet. This covers how to switch your Linux system between "Text Mode" (Server) and "Graphical Mode" (Desktop).

### **System Targets (Runlevels)**

|**Command**|**Description**|**Example**|
|---|---|---|
|**`systemctl get-default`**|Check which mode the system boots into.|`systemctl get-default`|
|**`systemctl set-default`**|Change the boot mode (persistent).|`systemctl set-default graphical.target`|
|**`multi-user.target`**|**CLI Mode:** Text-only (Server standard).|_(Runlevel 3)_|
|**`graphical.target`**|**GUI Mode:** Windows/Desktop interface.|_(Runlevel 5)_|
|**`systemctl isolate`**|Switch mode **immediately** (without reboot).|`systemctl isolate multi-user.target`|

---

### **Detailed Example Breakdown**

**1. Checking the current mode**

`systemctl get-default`

- **Output:** `multi-user.target`
    
- **Meaning:** The system is currently set to boot into a command-line interface (standard for servers to save RAM).
    

**2. Changing the boot mode**

`systemctl set-default graphical.target`

- **Action:** This updates a symbolic link. It tells `systemd`: "Next time we boot, load the Desktop Environment (GNOME/KDE)."
    
- **Output:** `Created symlink ... default.target → ... graphical.target`
    

**3. Starting it manually**

`systemctl start graphical.target`

- **Action:** You forced the graphical interface to load _right now_ without rebooting.



### **Detailed Breakdown**

**Command:**

`grep -e String /root/nautilus.xml | wc -l`

1. **`grep`**: The search tool (Global Regular Expression Print).
    
2. **`-e String`**: Specifies the **pattern** to search for.
    
    - _Note:_ You asked it to look for the exact text "String".
        
3. **`/root/nautilus.xml`**: The file being searched.
    
4. **`|` (Pipe)**: Takes the result of the search (the list of lines found) and passes it to the next command.
    
5. **`wc -l`**: Word Count with the **lines** flag.
    
    - Instead of printing the lines to the screen, it just counts them.
        

---

### **Interpreting Your Results**

- **Result `66`**:
    
    This means the word "String" was found on **66 lines** inside the file.
    
    _(If you just ran the `sed` command to replace "String" with "LUSV" and you still see 66, it means the replacement might not have worked, or there are still 66 instances left)._
    
- **Result `0`**:
    
    This means the word "About" was found **0 times**. It does not exist in the file.
    

---

### **Cheat Sheet Addition: Searching & Counting**

Here is the **Search (grep)** section for your cheat sheet.

|**Command**|**Description**|**Example**|
|---|---|---|
|**`grep`**|Search for text in a file.|`grep "error" log.txt`|
|**`grep -i`**|Search ignoring case (finds "Error", "ERROR").|`grep -i "error" log.txt`|
|**`grep -r`**|Recursive search (search inside all folders).|`grep -r "config" /etc/`|
|**`\| wc -l`**|Count the number of matches found.|`grep "User" file \| wc -l`|
### **Time & Date Management (timedatectl)**

|**Command**|**Description**|**Example**|
|---|---|---|
|**`timedatectl`**|Check current system time and timezone status.|`timedatectl`|
|**`timedatectl list-timezones`**|List all available timezones.|`timedatectl list-timezones`|
|**`timedatectl set-timezone`**|Change the system timezone.|`timedatectl set-timezone America/New_York`|

---

### **Detailed Example Breakdown**

**1. Search for the correct Timezone**

`timedatectl list-timezones | grep -i saipan`

- **`timedatectl list-timezones`**: This prints a massive list of every city/zone known to the system.
    
- **`| grep -i saipan`**: Since you don't want to scroll through thousands of lines, you pipe the output to `grep` to find "Saipan".
    
    - _Result:_ You found `Pacific/Saipan`.
        

**2. Apply the Change**

`timedatectl set-timezone Pacific/Saipan`

- **Action:** This updates the `/etc/localtime` file to match the new region.
    
- **Result:** Your "Local time" jumped from 17:59 (UTC) to 03:59 (ChST) automatically.


### **Firewall Management (firewalld)**

|**Command**|**Description**|**Example**|
|---|---|---|
|**`firewall-cmd --list-all`**|View all current rules (ports, services) for the default zone.|`firewall-cmd --list-all`|
|**`--add-port`**|Open a specific port.|`firewall-cmd --add-port=80/tcp`|
|**`--permanent`**|Write rule to config file (survives reboot).|`firewall-cmd --permanent ...`|
|**`--reload`**|Reload firewall to apply permanent changes.|`firewall-cmd --reload`|

---

### **Detailed Example Breakdown**

**1. Check Current Status**

`sudo firewall-cmd --zone=public --list-all`

- **`--zone=public`**: Firewalls have different "zones" (like Home, Work, Public). "Public" is the standard strict zone for servers.
    
- **Output:** You saw `ports:` was empty. No extra doors were open.
    

**2. Open Port 5001 (Permanently)**

`sudo firewall-cmd --zone=public --permanent --add-port=5001/tcp`

- **`--add-port=5001/tcp`**: Allow traffic on port 5001 using the TCP protocol.
    
- **`--permanent`**: **Crucial Flag!**
    
    - _Without this flag:_ The port opens _now_, but if you reboot the server, it closes again.
        
    - _With this flag:_ It saves the rule to the configuration file, but it does **not** open the port immediately in the live system.
        

**3. Apply the Changes**

`sudo firewall-cmd --reload`

- **Action:** This tells the firewall to re-read its configuration files.
    
- **Why?** Because you used `--permanent`, the change was only written to disk. The `reload` command pushes that saved config into the "live" runtime environment.
    

**4. Verify**

- The final `list-all` showed `ports: 5001/tcp`. Success!


### **System Resource Limits (limits.conf)**

|**Column**|**Description**|**Example**|
|---|---|---|
|**Domain**|The username or group (groups start with `@`).|`nfsuser` or `@developers`|
|**Type**|**Soft** (Warning level) or **Hard** (Absolute Maximum).|`soft` / `hard`|
|**Item**|What resource to limit (e.g., `nproc`, `nofile`, `fsize`).|`nproc`|
|**Value**|The specific number allowed.|`2048`|

---

### **Detailed Example Breakdown**

**The Configuration:**

`nfsuser soft nproc 1026`

`nfsuser hard nproc 2024`

**1. `nproc` (Number of Processes)**

- This rule restricts how many "tasks" or "processes" the user `nfsuser` can run simultaneously.
    
- _Why?_ This prevents accidental "fork bombs" (where a script runs out of control and spawns infinite copies of itself, freezing the server).
    

**2. Soft vs. Hard Limits**

- **Soft Limit (`1026`):** This is the "Safety Zone."
    
    - The user is allowed to exceed this number temporarily, but they might get warnings.
        
    - The user _can_ change this limit themselves (up to the Hard limit) using the `ulimit` command.
        
- **Hard Limit (`2024`):** This is the "Brick Wall."
    
    - The user cannot go above this number.
        
    - Only `root` can increase this limit.
        
    - If `nfsuser` tries to start the 2,025th process, the system will simply say "Resource temporarily unavailable" and deny it.

### **SELinux Management**

|**Command**|**Description**|**Example**|
|---|---|---|
|**`sestatus`**|Check current SELinux status.|`sestatus`|
|**`setenforce 0`**|Switch to **Permissive** mode (temp).|`setenforce 0`|
|**`setenforce 1`**|Switch to **Enforcing** mode (temp).|`setenforce 1`|
|**`/etc/selinux/config`**|Config file for **Permanent** changes.|`vi /etc/selinux/config`|
|**`yum install`**|Install packages (RedHat/CentOS).|`yum install package_name`|

---

### **Detailed Example Breakdown**

**1. Install Tools**

`sudo yum install selinux-policy...`

- **`yum`**: The package manager for CentOS/RedHat (similar to `apt` on Ubuntu).
    
- **Action:** You ensured the core SELinux software was actually installed before trying to configure it.
    

**2. Disable Permanently**

`vi /etc/selinux/config`

- **Action:** You changed `SELINUX=enforcing` to `SELINUX=disabled`.
    
- **The Modes:**
    
    - **`Enforcing`**: The guard is active. If a rule is broken, it blocks the action AND logs it.
        
    - **`Permissive`**: The guard is watching but lazy. If a rule is broken, it lets it happen but **logs it** (good for troubleshooting).
        
    - **`Disabled`**: The guard is gone. No blocking, no logging.
        

**3. The "Reboot" Rule**

- **Important:** Changing the config file to `disabled` requires a **REBOOT** to take effect.
    
- **Why?** SELinux loads very early in the boot process (inside the Kernel). You can't fully turn it off while the system is running.
    
- _Note:_ If you just wanted to stop it temporarily without rebooting, you would use `sudo setenforce 0`.


### **What this command does**

It essentially asks the system: _"If I were logged in as `nfsuser`, what is the absolute maximum number of processes (Hard Limit) I would be allowed to run?"_

Based on your previous edit (`nfsuser hard nproc 2024`), the output should be: **`2024`**

---

### **Detailed Command Breakdown**

`sudo su -c "su -c 'ulimit -Hu' -s /bin/sh nfsuser"`

1. **`sudo su -c "..."`**: Runs the enclosed command as **Root**. (This is needed because usually only root can switch to other users without a password).
    
2. **`su ... nfsuser`**: Switch from Root to **nfsuser**.
    
3. **`-s /bin/sh`**: **Override the Shell.**
    
    - _Why is this here?_ System users (like `nfsuser`) often have their shell set to `/sbin/nologin` for security, meaning you can't normally log in as them. This flag forces the system to use a valid shell (`/bin/sh`) just for this one command, allowing it to run.
        
4. **`-c 'ulimit -Hu'`**: The actual check.
    
    - **`-H`**: Check the **H**ard limit (the maximum ceiling).
        
    - **`-u`**: Check the **u**ser process limit (`nproc`).


### **The Command**

Bash

```
ls -a1 /etc/ > /root/etc_file_list.txt
```

### **Detailed Breakdown**

|**Component**|**Description**|
|---|---|
|**`ls`**|The list command.|
|**`-a`**|**All**: Includes hidden files, as well as `.` (current directory) and `..` (parent directory).|
|**`-1`**|**One**: Forces the output to list **one file per line**.|
|**`/etc/`**|The source directory you are listing.|
|**`>`**|**Redirects** the output into the file (overwriting it).|
|**`/root/etc_file_list.txt`**|The destination file path.|

---

### **Verification**

To check if the file was created correctly and contains the data:

Bash

```
head -n 5 /root/etc_file_list.txt
```


### **2. The Verification Step**

To verify this worked, you generally check two things: **Format** and **Content**.

**A. Checking the Format (Visual)**

Bash

```
head -n 5 /root/etc_file_list.txt
```

- **What it does:** Shows the first 5 lines of the new file.
    
- **Why it works:** You should immediately see `.` and `..` at the very top. If you see them, you know you used the `-a` flag correctly. If the list is vertical, you know `-1` worked.
    

**B. Checking the Count (Mathematical)**

Bash

```
wc -l /root/etc_file_list.txt
```

- **What it does:** Counts the number of **lines** in the file.
    
- **Why it works:** You can compare this number to the actual number of files in the directory.
    
    - _Command to compare:_ `ls -a1 /etc/ | wc -l`
        
    - If the number in your text file matches the number from the live command, your file is a perfect snapshot of the directory.


```
/home/bob
[root@centos-host bob]# cd backup
bash: cd: backup: No such file or directory
[root@centos-host bob]# cp -b /etc/hosts /backup/system_configs/hosts.bak
[root@centos-host bob]# cat -b /etc/hosts /backup/system_configs/hosts.bak
     1  # Kubernetes-managed hosts file.
     2  127.0.0.1       localhost
     3  ::1     localhost ip6-localhost ip6-loopback
     4  fe00::0 ip6-localnet
     5  fe00::0 ip6-mcastprefix
     6  fe00::1 ip6-allnodes
     7  fe00::2 ip6-allrouters
     8  192.168.144.245 centos-host

     9  # Entries added by HostAliases.
    10  10.0.0.6        docker-registry-mirror.kodekloud.com
    11  # Kubernetes-managed hosts file.
    12  127.0.0.1       localhost
    13  ::1     localhost ip6-localhost ip6-loopback
    14  fe00::0 ip6-localnet
    15  fe00::0 ip6-mcastprefix
    16  fe00::1 ip6-allnodes
    17  fe00::2 ip6-allrouters
    18  192.168.144.245 centos-host

    19  # Entries added by HostAliases.
    20  10.0.0.6        docker-registry-mirror.kodekloud.com

```

Here is how the terminal output proves it:

1. **The Copy Worked:** The command `cp -b /etc/hosts /backup/system_configs/hosts.bak` successfully copied the file. If the folder didn't exist or permissions were wrong, you would have seen an error message immediately.
    
2. **The Content Matches:** You used `cat -b` to display **both** files at once.
    
    - **Lines 1–10** display the original `/etc/hosts`.
        
    - **Lines 11–20** display your new copy `/backup/system_configs/hosts.bak`.
        
    - Since lines 11–20 are identical to 1–10, the copy is perfect.
        

### **A Note on the `-b` Flag**

You used `cp -b` (backup).

- **What it does:** If `hosts.bak` _already_ existed in that folder, `cp -b` would have renamed the old one (usually to `hosts.bak~`) before pasting the new one.
    
- **Is it wrong?** No, it is a safe and smart habit, though for a simple copy instruction, just `cp` (without flags) is standard.
    

### **Summary for Cheat Sheet**

| **Command**             | **Description**                                                |     |
| ----------------------- | -------------------------------------------------------------- | --- |
| **`cp source dest`**    | Standard copy.                                                 |     |
| **`cp -b source dest`** | Copy, but if destination exists, make a backup of it first.    |     |
| **`cat -b file`**       | Display file content with line numbers (non-blank lines only). |     |
### **Hostname Configuration**

|**Command**|**Description**|**Example**|
|---|---|---|
|**`hostname`**|View the current system name.|`hostname`|
|**`hostname -i`**|View the IP address associated with the hostname.|`hostname -i`|
|**`hostnamectl`**|**Modern Way:** View detailed system info (OS, Kernel, Architecture).|`hostnamectl`|
|**`hostnamectl set-hostname`**|**Persistent Change:** Set a new name that survives reboot.|`hostnamectl set-hostname web-server-01`|

---

### **Detailed Example Breakdown**

**1. Viewing the Name**

Bash

```
[root@stapp01 ~]# hostname
stapp01.stratos.xfusioncorp.com
```

**2. Changing the Name (The Old vs. New Way)**

- **Temporary (Old Way):**
    
    `hostname new-name`
    
    - _Result:_ The name changes immediately, but if you reboot, it goes back to the old name.
        
- **Permanent (New Way - Systemd):**
    
    `hostnamectl set-hostname new-name`
    
    - _Result:_ This updates the `/etc/hostname` file automatically. The name change is permanent.


Here is the command to count the total number of lines in `/etc/services`.

### **The Command**

Bash

```
wc -l /etc/services
```

### **Explanation**

- **`wc`**: Stands for **W**ord **C**ount.
    
- **`-l`**: The "lines" flag. It tells the command to count newline characters only.
    
- **`/etc/services`**: The file path you are checking.
    

**Example Output:**

Bash

```
11473 /etc/services
```

_(This means there are 11,473 lines in that file)._

### **Alternative (Clean Number)**

If you want **only** the number (without the filename printed next to it), you can pipe the file content into the command:

Bash

```
cat /etc/services | wc -l
```




Bash

```
find /etc -type f -name "*.conf" > /root/etc_conf_files.txt
```

### **Detailed Breakdown**

|**Component**|**Description**|
|---|---|
|**`find`**|The search tool.|
|**`/etc`**|The directory where the search starts.|
|**`-type f`**|Ensures you are looking for **files** only (ignores directories that might end in .conf).|
|**`-name "*.conf"`**|The search pattern. The asterisk `*` is a wildcard meaning "anything before .conf".|
|**`>`**|Redirects the list of found files into the target file.|
|**`/root/etc_conf_files.txt`**|The destination file.|

### **Verification**

To check if the file was created and has content:

Bash

```
wc -l /root/etc_conf_files.txt
```


The `tee` command is ==a standard command-line utility in Unix and Linux systems that reads from **standard input** and writes the output to both **standard output** (the terminal screen) and one or more **files** simultaneously==. 

It is named after a T-shaped pipe fitting, as it splits the data flow into two or more directions. This functionality is especially useful for monitoring a command's output in real-time while also saving it to a log file for future analysis or debugging. 

Syntax

The basic syntax is as follows:

bash

```
command | tee [OPTIONS] [FILE...]
```

- `command`: The initial command whose output you want to redirect.
- `|` (pipe): Redirects the standard output of the preceding command to the standard input of `tee`.
- `tee`: The command itself.
- `[OPTIONS]`: Optional flags to modify behavior.
- `[FILE...]`: One or more files where the output will be saved. 

Common Options

- `-a`, `--append`: Appends the output to an existing file instead of overwriting its content.
- `-i`, `--ignore-interrupts`: Ignores interrupt signals (like those generated by pressing `Ctrl+C`). 

Examples

- **View output and save to a file:**
    
    bash
    
    ```
    ls -l | tee directory-listing.txt
    ```
    
    This command will display the directory listing on the screen and save the same output to `directory-listing.txt`.
- **Append output to an existing file:**
    
    bash
    
    ```
    uptime | tee -a system-log.txt
    ```
    
    This appends the current system uptime information to `system-log.txt` without erasing previous entries.
- **Write to a privileged file using `sudo`:**
    
    bash
    
    ```
    echo "some text" | sudo tee /path/to/root_file > /dev/null
    ```
    
    Standard shell redirection (`>`) happens before `sudo` executes the command, which would cause a permission error if the target file is owned by root. Using `tee` with `sudo` elevates the privileges for the writing process itself, allowing the operation to succeed. Redirecting standard output to `/dev/null` suppresses the mirrored output in the console if desired.
- **Write to multiple files simultaneously:**
    
    bash
    
    ```
    echo "Hello World" | tee file1.txt file2.txt file3.txt
    ```