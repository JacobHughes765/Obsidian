
This cheat sheet covers common tasks and commands for managing a Debian-based system. It includes package management, system administration, file operations, networking, and more.

## Package Management (APT)

- Update package lists: `sudo apt update`
- Upgrade installed packages: `sudo apt upgrade`
- Install a package: `sudo apt install <package_name>`
- Remove a package: `sudo apt remove <package_name>`
- Remove unused packages: `sudo apt autoremove`
- Search for a package: `apt search <keyword>`
- Show package details: `apt show <package_name>`
- List installed packages: `dpkg -l`
- Clean up cached packages: `sudo apt clean`

## System Information

- Check Debian version: `cat /etc/debian_version`
- Display system info: `uname -a`
- Show CPU details: `lscpu`
- Display memory usage: `free -h`
- List disk usage: `df -h`
- Show running processes: `top` or `htop`
- Check system uptime: `uptime`

## File and Directory Operations

- List files and directories: `ls -l`
- Change directory: `cd /path/to/directory`
- Create a directory: `mkdir <directory_name>`
- Remove a file: `rm <file_name>`
- Remove a directory: `rm -r <directory_name>`
- Copy files: `cp <source> <destination>`
- Move or rename files: `mv <source> <destination>`
- View file contents: `cat <file_name>`
- Edit a file: `nano <file_name>` or `vim <file_name>`
- Find a file: `find / -name <file_name>`
- Search file contents: `grep <pattern> <file_name>`

## User and Group Management

- Add a new user: `sudo adduser <username>`
- Delete a user: `sudo deluser <username>`
- Add user to a group: `sudo usermod -aG <group_name> <username>`
- Change user password: `sudo passwd <username>`
- List groups: `cat /etc/group`
- Switch user: `su - <username>`

## Permissions

- Change file permissions: `chmod <mode> <file_name>` (e.g., `chmod 755 script.sh`)
- Change file ownership: `chown <user>:<group> <file_name>`
- View permissions: `ls -l`

## System Administration

- Restart the system: `sudo reboot`
- Shut down the system: `sudo shutdown -h now`
- Check running services: `systemctl list-units --type=service`
- Start a service: `sudo systemctl start <service_name>`
- Stop a service: `sudo systemctl stop <service_name>`
- Enable a service at boot: `sudo systemctl enable <service_name>`
- Disable a service at boot: `sudo systemctl disable <service_name>`
- Check service status: `systemctl status <service_name>`
- View system logs: `journalctl -u <service_name>`
- Update system time: `sudo timedatectl set-time 'YYYY-MM-DD HH:MM:SS'`

## Networking

- Check network interfaces: `ip addr`
- Display network status: `ifconfig`
- Test network connectivity: `ping <hostname>`
- View open ports: `netstat -tuln`
- Check network services: `ss -tuln`
- Restart networking: `sudo systemctl restart networking`
- Edit network configuration: `sudo nano /etc/network/interfaces`
- View DNS settings: `cat /etc/resolv.conf`

## Process Management

- List all processes: `ps aux`
- Kill a process by ID: `kill <pid>`
- Kill a process by name: `pkill <process_name>`
- Run a process in the background: `<command> &`
- View background jobs: `jobs`
- Bring a job to the foreground: `fg <job_number>`

## Disk and Filesystem Management

- List mounted filesystems: `mount`
- Check disk space: `du -sh /path`
- Format a disk: `sudo mkfs.<type> /dev/<disk>` (e.g., `mkfs.ext4 /dev/sdb1`)
- Mount a device: `sudo mount /dev/<disk> /mnt`
- Unmount a device: `sudo umount /mnt`
- Check disk health: `sudo smartctl -a /dev/<disk>`

## Software Installation (Alternatives to APT)

- Install from .deb file: `sudo dpkg -i <package.deb>`
- Install software from source:
    
    ```bash
    ./configure
    make
    sudo make install
    ```
    
- Install Python packages: `pip install <package_name>`
- Install Node.js packages: `npm install <package_name>`

## System Updates

- Perform a full system upgrade: `sudo apt full-upgrade`
- Check for security updates: `sudo apt update && apt list --upgradable`
- Apply security patches: `sudo unattended-upgrades`

## Troubleshooting

- View system logs: `dmesg`
- Check disk errors: `sudo fsck /dev/<disk>`
- Repair broken dependencies: `sudo apt install -f`
- Recover GRUB bootloader: `sudo grub-install /dev/<disk>`
- Check kernel version: `cat /proc/version`

## Useful Tools

- Install essential tools: `sudo apt install vim nano curl wget git`
- Monitor system resources: `htop` (install with `sudo apt install htop`)
- Archive files: `tar -czvf <archive.tar.gz> <directory>`
- Extract tar files: `tar -xzvf <archive.tar.gz>`

## Cron Jobs

- Edit cron jobs: `crontab -e`
- List cron jobs: `crontab -l`
- Example cron job (run script daily at 2 AM):
    
    ```bash
    0 2 * * * /path/to/script.sh
    ```
    

## SSH

- Connect to a remote server: `ssh <username>@<hostname>`
- Copy files over SSH: `scp <file> <username>@<hostname>:/path`
- Enable SSH server: `sudo systemctl enable ssh`
- Start SSH server: `sudo systemctl start ssh`

## Backup

- Create a backup with rsync: `rsync -av /source /destination`
- Create a compressed backup: `tar -czvf backup.tar.gz /path/to/backup`

## Environment Variables

- Set a temporary variable: `export VAR_NAME=value`
- Make variable persistent: Add `export VAR_NAME=value` to `~/.bashrc`
- Reload .bashrc: `source ~/.bashrc`

## Useful Files and Directories

- System configuration: `/etc`
- User home directory: `~/`
- Log files: `/var/log`
- Package sources: `/etc/apt/sources.list`

This cheat sheet provides a quick reference for common Debian tasks. For more details, use `man <command>` or `<command> --help`.