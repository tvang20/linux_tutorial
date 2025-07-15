# Linux Environment Tutorial (using `venv`)

This is a tutorial for how to use and navigate environments in Linux using Python’s built-in `venv` module.  
You need to have **Python 3.3+ installed** (with `python3-venv` available).  
These instructions also apply to HPC (High Performance Computing) environments.

---

## 1. Check Python Version and `venv` Availability

```bash
python3 --version               # Check Python version
python3 -m venv --help          # Check if venv is available
```

If `venv` is not available:

```bash
sudo apt install python3-venv
```

---

## 2. Create a Folder to Store Environments

```bash
cd ~
mkdir -p ~/envs                 # Folder for all your environments
```

---

## 3. Create and Activate Your First Environment

```bash
python3 -m venv ~/envs/guo_lab        # Create environment
source ~/envs/guo_lab/bin/activate    # Activate it
```

When activated, you will see `(guo_lab)` in your prompt.

To deactivate:

```bash
deactivate
```

---

## 4. Install Python Packages

```bash
pip install numpy
pip install pandas
```

These packages are installed locally inside the environment.

---

## 5. Environment Management Commands

| Command | Description |
|--------|-------------|
| `pip list` | Show installed packages |
| `pip freeze > requirements.txt` | Save environment to file |
| `pip install -r requirements.txt` | Install packages from file |

💡 **Tip**: Create a base environment with common packages. Later, duplicate it and add project-specific packages as needed.

---

# Useful Linux Commands

A categorized list of essential Linux commands to help you navigate, manage files, work with environments, and monitor systems.

---

## 🔍 Navigation

```bash
pwd                    # Show current directory
ls                     # List files
ls -l                  # Long listing with permissions
ls -a                  # Include hidden files
cd dir_name            # Change directory
cd ..                  # Go up one directory
cd ~                   # Go to home directory
tree                   # Show directory tree (install with `sudo apt install tree`)
```

---

## 📁 File & Directory Management

```bash
mkdir folder_name              # Create new directory
mkdir -p path/to/folder        # Create nested folders
rm file.txt                    # Delete a file
rm -r folder/                  # Delete a directory
cp file1.txt file2.txt         # Copy file
cp -r dir1/ dir2/              # Copy folder recursively
mv old_name.txt new_name.txt   # Move or rename
touch newfile.txt              # Create empty file
```

---

## 📄 Viewing & Editing Files

```bash
cat file.txt                   # Print contents
less file.txt                  # Scroll through a file (q to quit)
head file.txt                  # First 10 lines
tail file.txt                  # Last 10 lines
nano file.txt                  # Open file in nano editor
vim file.txt                   # Open file in Vim
code file.txt                  # Open in VS Code (if installed)
```

---

## 🔎 Searching

```bash
grep "pattern" file.txt         # Search for a pattern in a file
grep -r "pattern" ./folder      # Search recursively in directory
find . -name "*.py"             # Find all .py files
locate filename                 # Find files by name (run `updatedb` first)
```

---

## 📦 Package Management (Debian/Ubuntu)

```bash
sudo apt update                 # Refresh package lists
sudo apt upgrade                # Upgrade all installed packages
sudo apt install package_name   # Install a package
sudo apt remove package_name    # Remove a package
```

---

## 🧪 Python & Environments

```bash
python3 --version                       # Check Python version
python3 -m venv myenv                   # Create virtual environment
source myenv/bin/activate               # Activate environment
deactivate                              # Deactivate environment
pip install package_name                # Install Python package
pip list                                # List installed packages
pip freeze > requirements.txt           # Save installed packages
pip install -r requirements.txt         # Install from file
rm -r /path/to/environment/             # Delete the environment
```

---

## ⚙️ Permissions & Executing Scripts

```bash
chmod +x script.sh             # Make script executable
./script.sh                    # Run executable script
squeue -u $USER                # Show your jobs (SLURM)
sbatch script.sh               # Submit a batch job
scancel JOB_ID                 # Cancel a job
```

---

## 🖥️ System Monitoring

```bash
top                            # Show system processes
htop                           # Improved top (install: `sudo apt install htop`)
ps aux                         # List all processes
kill PID                       # Kill process by PID
free -h                        # Show memory usage
df -h                          # Disk usage (human-readable)
du -sh *                       # Folder sizes in current directory
```

---

## 🌐 Networking

```bash
ping google.com                # Test internet connection
curl http://example.com        # Fetch web page
wget http://example.com/file   # Download file
scp file user@host:/path       # Secure file copy
ssh user@remote_ip             # SSH into remote system

git clone https://github.com/username/repo-name.git  # Clones the github folder
```

---

## 🧰 Other Utilities

```bash
history                        # Show command history
alias ll='ls -lah'             # Set command shortcut
clear                          # Clear terminal screen
echo $PATH                     # Show environment PATH variable
which command_name             # Find full path of a command
man ls                         # Manual/help page for a command

To rerun commands from history, you can use ! followed by the command number, EXP "!356"
```

---

## 💡 Tips

- Use `TAB` to auto-complete file and folder names.
- Use `CTRL + C` to cancel a running command.
- Use `CTRL + D` to log out or exit terminal.

## Notes

- Always activate the environment before installing packages or running Python scripts.
- Keep your `requirements.txt` under version control for reproducibility.
