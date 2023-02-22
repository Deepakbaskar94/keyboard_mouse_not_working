# keyboard_mouse_not_working
keyboard and mouse not working issue

sudo apt-get install xserver-xorg-input-all

# Dependency unmet issue
https://unix.stackexchange.com/questions/673340/unmet-dependencies-ubuntu-desktop




What worked for me:
I simply installed the task-package of ubuntu-desktop. You can install it by:

sudo apt install ubuntu-desktop^
^ means task package

If you prefer GUI:

sudo apt install tasksel
sudo tasksel
# arrow keys to navigate and space bar to select.
select ubuntu desktop and press enter

Some other things to try:
First, try updating the repositories:

sudo apt update
If that didn't worked, try using force install:

sudo apt -f install ubuntu-desktop
You can also try using aptitude:

# install aptitude
sudo apt install aptitude

# install the packages
sudo aptitude install ubuntu-desktop

## aptitude will suggest solutions to fix the error, if you find them ok then accept the solutions.
Using aptitude with -f parameter.

sudo aptitude -f install ubuntu-desktop
Using -f with task package:

sudo aptitude -f install ubuntu-desktop^
Try removing error .deb files from apt cache directory.

sudo rm /var/cache/apt/archives/*.deb
Try clearing of the status of conflicting packages:

# create a backup first:
sudo cp -r /var/lib/dpkg/status /var/lib/dpkg/status.bak

# view the file:
view /var/lib/dpkg/status
# Now, find the information given about the error packages and try removing it.
Try installing the dependencies, yourself:

sudo apt install <package>
Try installing the normal version of the package i.e gnome-session

sudo apt -f install gnome-session
Feel free to edit and add more solutions.
