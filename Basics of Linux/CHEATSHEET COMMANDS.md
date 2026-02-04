
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
| **`cp`**       | Copy a file.                          | `cp file1 file2`     |
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
    
