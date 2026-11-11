# **Linux Commands for Cloud Computing**

Practical commands for checking memory, disk, and package health on a Linux cloud server (tested on Ubuntu 22.04).

## **Check Free Memory on Virtual Private Server (VPS)**

### 1. Quick overview

```bash
free -h
```

Look at the **available** column. It shows memory that can be used without swapping, and it matters more than the **free** column.

### 2. Check disk space

Low disk space often shows up together with low memory.

```bash
df -h /
```

```bash
sudo du -xhd1 /var 2>/dev/null
```

```bash
sudo journalctl --disk-usage
```

- `df -h /` shows total, used, and free space on the main disk.
- `du -xhd1 /var` shows which folders under `/var` use the most space.
- `journalctl --disk-usage` shows how much space system logs take.

### 3. Check swap

```bash
swapon --show
```

No output means no swap is active.

### 4. Find which processes use the most memory

```bash
ps aux --sort=-%mem | head -n 10
```

Shows the top 10 processes by memory use.

### 5. Detailed memory info

```bash
head -n 5 /proc/meminfo
vmstat 1 5
```

- `/proc/meminfo` shows total, free, and available memory in detail.
- `vmstat 1 5` prints 5 snapshots, one per second. Watch the `si` and `so` columns: values above zero mean the system is swapping.

### 6. Live view

```bash
top
```

Press **M** to sort by memory and **q** to quit.

### 7. Check for stuck package processes

```bash
ps aux | grep -E "apt|dpkg"
sudo dpkg --audit
```

- The first command lists running package processes.
- `dpkg --audit` reports packages that are half-installed or misconfigured. No output means everything is fine.

!!! Warning

Do not kill package processes or delete lock files until you know what they are.