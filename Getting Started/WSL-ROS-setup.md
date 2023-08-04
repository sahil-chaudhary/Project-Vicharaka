All of these can easily be accessed in the relevant docs, this is just a compilation after having trimmed out unnecessary checks not important to a default WSL install, if you face issues you can look in the docs and run the more extensive checks present there

[WSL Installation](https://learn.microsoft.com/en-us/windows/wsl/install)

[ROS Installation](https://docs.ros.org/en/humble/Installation/Ubuntu-Install-Debians.html)

Windows Terminal is recommended

### Step 1: get WSL
If you have Ubuntu 22.04 installed already skip this step

For Windows 11/Windows 10 version 2004+: Open command prompt/powershell as an administrator and run `wsl --install -d Ubuntu-22.04` ; wait for it to get installed and follow the on screen setup (you may need to reboot your pc)

For older versions: [Manual installation](https://learn.microsoft.com/en-us/windows/wsl/install-manual)

After logging in, run `sudo apt update && sudo apt upgrade` for updating system packages

### Step 2: get ROS 
In the linux shell first add the required GPG key and repo
```
sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(. /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null
sudo apt update
```
Install ROS: `sudo apt install ros-humble-desktop`

### Step 3: Further setup and testing
You need to run `source /opt/ros/humble/setup.bash` in every shell session before being able to use ROS commands. In order to make this automatic, edit `~/.bashrc` in the linux distribution and add this line to the bottom of the script (eg `nano ~/.bashrc`).

For testing open one shell, run `ros2 run demo_nodes_cpp talker` and in a second shell run `ros2 run demo_nodes_py listener` (remember to have the source command performed first, you need to do it every shell you open if it's not in .bashrc). You should be able to see some output on the listener side

You can now continue development, see [turtlesim](https://docs.ros.org/en/humble/Tutorials/Beginner-CLI-Tools/Introducing-Turtlesim/Introducing-Turtlesim.html). Note that the packages mentioned in the documentation are already installed in the previous steps

### Further notes
- If you're having some issues you can try force exiting wsl (`wsl --shutdown`) in a windows shell and then try again, if it persists also try rebooting
