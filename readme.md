# Automatic Update
## An daemon for Debian/Ubuntu to update the repositories and update packages

### How it works
It's a simple bash script that executes `apt update && apt upgrade -y` automatically, there's also a script that's install for you the service and the script to update, and you can select a server option to update and install packages every 8 hours.

### LOG file
There's a log file generated in `/tmp/update_status.log`, if you run in trouble, execute `cat /tmp/update_status.log`, so you can check what's wrong (A little observation: the apt itself says that it's don't have a stable CLI interface, so check the first updates to see if any of your repositories has any issue, so far in myy tests, I hadn't nay problem or issue, even in my server)

### How to install
The script of installation itself it's pretty simple, first you unzip and you'll find a directory called .update (with a update script inside) and the install script (with the same name). After unzip the folder, execute the command below:

`cd update_service && sudo chmod 755 install`

After turning the script executable, execute the same (**NOTE: Execute with `sudo `command, like below**)

`sudo ./install`

If you're running on a server, like said before, you can run the `--server` argument to update every 8 hours, like this:

`sudo ./install --server`

After that the automatic update is installed!

### The reason for this script
In systems like Ubuntu and Debian, every time I booted up the PC, appears the notification to update the packages, and futhermore, my servers has keeped too many days without a update, to solve this, I develop this script, it was the first of my SysAdmin carrer (that's the carrer I want to follow).