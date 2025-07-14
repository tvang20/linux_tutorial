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

## 6. Useful Linux Commands

| Command | Description |
|---------|-------------|
| `chmod +x script.sh` | Make script executable |
| `./script.sh` | Run an executable script |

---

## Notes

- Always activate the environment before installing packages or running Python scripts.
- Keep your `requirements.txt` under version control for reproducibility.
