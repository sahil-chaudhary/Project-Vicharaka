All of these can easily be accessed in the relevant docs, this is just a compilation after having trimmed out unnecessary checks not important to a default WSL install, if you face issues you can look in the docs and run the more extensive checks present there

[WSL Installation](https://learn.microsoft.com/en-us/windows/wsl/install); [ROS Installation](http://wiki.ros.org/noetic/Installation/Ubuntu)

Windows Terminal is recommended

### Step 1: get WSL
If you have Ubuntu 20.04 installed already skip this step

For Windows 11/Windows 10 version 2004+: Open command prompt/powershell as an administrator and run `wsl --install -d Ubuntu-20.04`; wait for it to get installed and follow the on screen setup (you may need to reboot your pc)

For older versions: [Manual installation](https://learn.microsoft.com/en-us/windows/wsl/install-manual)

After logging in, run `sudo apt update && sudo apt upgrade` for updating system packages

### Step 2: get ROS 
In the linux shell first add the required GPG key and repo
```
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
sudo apt update
```
Install ROS: `sudo apt install ros-noetic-desktop-full`

You need to run `source /opt/ros/noetic/setup.bash` in every shell session before being able to use ROS commands. In order to make this automatic, edit `~/.bashrc` in the linux distribution and add this line to the bottom of the script.

To verify installation, run `printenv | grep ROS`, you should see a whole bunch of ros specific environment variables

You are now installed, and can make a workspace and start coding (see [workspaces](http://wiki.ros.org/ROS/Tutorials/InstallingandConfiguringROSEnvironment) for more details, or go into [tutorials](http://wiki.ros.org/ROS/Tutorials/NavigatingTheFilesystem)

For workspace creation, make a folder with a subfolder called src, and then run `catkin-make`
```
mkdir -p ~/test_workspace/src
cd ~/test_workspace
catkin_make
```
You also need to run the setup file in the generated `devel` subfolder, do `source <workspace_dir>/devel/setup.bash` (this also needs to be done on every shell session


### Further notes
- If you're having some issues you can try force exiting wsl (`wsl --shutdown`) in a windows shell and then try again, if it persists also try rebooting
