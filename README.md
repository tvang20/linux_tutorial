# linux_tutorial

This is a tutorial for how to use and navigate through environments in linux. We will be creating environments using the built-in venv python module. You need to have python 3.3+ install as ADMIN.
The same thing can be done on the HPC.

1) Checking our python version and seeing if venv is installed, if not we will install it.
  A) $python3 --version
  B) $python3 -m venv --help
  C) If you need to install $sudo apt install python3-venv

3) Next, we're going to create a folder to STORE all our environments.
   A) Make sure you're at the home directory.
   B) $mkdir -p ~/envs

4) We are now going to create our FIRST environment and activate it.
   A) $python3 -m venv ~/envs/guo_lab
   B) $source ~/envs/guo_lab/bin/activate
       You should have "guo_lab" next to your computer name.
   C) $deactivate: deactivates the current enviroment.

5) Installing some packages
    A) $pip install numpy
    B) $pip install pandas

6) List of IMPORTANT COMMANDS
  A) $pip list: Checking what packages are INSTALL in the environment
  B) $pip freeze > requirements.txt: Will store all packages into an txt file in case you need to duplicate environment
     $pip freeze: prints the version of each package installed.
  C) $pip install -r /path/to/requirements.txt: If you want to duplicate the current enviroment, you can create a NEW enviroment and use this command.
      # For example, you have a base enviroment that encapsulates majority of the packages that are needed, but you only want to install a few new ones for a new project.

7) OTHER useful linux commands
   A) chmod +x script.sh : makes the script you created executable.
   B) ./script.sh : executes the script
