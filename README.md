# ROS-Noetic-ROS2-Foxy-on-Ubuntu-20.04 

# Task 1: Install ROS noetic & Install ROS2 foxy on Ubuntu 20.04 

## Description 
This repository provides detailed guidelines for installing ROS Noetic and ROS2 Foxy on Ubuntu 20.04. By following these steps, you can establish a robust development environment for your robotics projects.

---

### Prerequisites

* Download Ubuntu 20.04 desktop image from [here](https://releases.ubuntu.com/20.04/)
* Open VirtualBox and create a new virtual machine.
* Follow this [guide](https://www.wikihow.com/Install-Ubuntu-on-VirtualBox) to install Ubuntu 20.04 on VirtualBox.

---

### Install ROS Noetic

If you haven't already, start by installing Ubuntu 20.04 on VirtualBox. Here's how:

1. **Download Ubuntu 20.04 ISO:**
   - Visit the [Ubuntu download page](https://releases.ubuntu.com/20.04/) and download the Ubuntu 20.04 desktop image.

2. **Create a Virtual Machine in VirtualBox:**
   - Open VirtualBox and click on "New" to create a new virtual machine.
   - Follow the wizard to set up the virtual machine, allocating memory and creating a virtual hard disk.
  ![image](https://github.com/GDHadeel/ROS-Noetic-ROS2-Foxy-on-Ubuntu-20.04/assets/126657301/9aa347d9-ef84-4859-94be-edb7d6bbd699)

3. **Install Ubuntu 20.04:**
   - Select the Ubuntu 20.04 file as the startup disk for the virtual machine.
   - Follow the on-screen instructions to install Ubuntu 20.04 within the virtual machine.
  ![image](https://github.com/GDHadeel/ROS-Noetic-ROS2-Foxy-on-Ubuntu-20.04/assets/126657301/041b70cd-af33-45e7-a0a8-91bf92aa9bec)

4. **Open Terminal:**
   - Once Ubuntu 20.04 is installed and booted up, open a terminal window (`Ctrl + Alt + T`).
  ![image](https://github.com/GDHadeel/ROS-Noetic-ROS2-Foxy-on-Ubuntu-20.04/assets/126657301/f3ea4708-6802-4782-ae08-6eb91aaf6624)

   
#### Install ROS Noetic

Now, let's install ROS Noetic:

1. **Setup your sources.list:**
   - Open a terminal and enter the following command to set up your sources list:
     ```bash
     sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
     ```

2. **Set up your keys:**
     ```bash
     sudo apt install curl # if you haven't already installed curl
     curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
     ```
3. **Installation:**
   - First, make sure your Debian package index is up-to-date:
     ```bash
     sudo apt update
     ```

4. **Desktop-Full Install: (Recommended) :**
     ```bash
     sudo apt install ros-noetic-desktop-full
     ```
5. **Environment setup:**
   - You must source this script in every bash terminal you use ROS in.
     ```bash
     source /opt/ros/noetic/setup.bash
     ```
     
6. **Environment setup:**
   - To install this tool and other dependencies for building ROS packages, run:
     ```bash
     sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential
     ```
     
   - Initialize rosdep
     ```bash
     sudo apt install python3-rosdep
     ```

   - With the following, you can initialize rosdep.
     ```bash
     sudo rosdep init
     rosdep update
     ```
     
![image](https://github.com/GDHadeel/ROS-Noetic-ROS2-Foxy-on-Ubuntu-20.04/assets/126657301/0b26a171-990a-4e3d-ab57-8319b733f05c)

---

### Install ROS2 Foxy

Follow these steps to install ROS2 Foxy on Ubuntu 20.04:

1. **Setting Locale to UTF-8:**
     ```bash
     locale  # check for UTF-8

     sudo apt update && sudo apt install locales
     sudo locale-gen en_US en_US.UTF-8
     sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8
     export LANG=en_US.UTF-8
     
     locale  # verify settings
     ```

2. **Setup Sources:**
   1. Ubuntu Universe repository enable
     ```bash
     sudo apt install software-properties-common
     sudo add-apt-repository universe
     ```
     
   2. add ROS 2 GPG key
     ```bash
     sudo apt update && sudo apt install curl -y
     sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg
     ```

   3. add repository to sources list
     ```bash
     echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(. /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null
     ```

4. **Install ROS2 packages:**
   - Update your package index and install ROS 2 packages:
     ```bash
     sudo apt update
     sudo apt upgrade
     
     sudo apt install ros-foxy-desktop python3-argcomplete
     sudo apt install ros-foxy-ros-base python3-argcomplete
     sudo apt install ros-dev-tools
     ```

5. **Environment setup:**
   - Set up your environment by sourcing the following file:
     ```bash
     # Replace ".bash" with your shell if you're not using bash
     # Possible values are: setup.bash, setup.sh, setup.zsh
     source /opt/ros/foxy/setup.bash
     ```

6. **Try some examples:**
   - If you installed ros-foxy-desktop above you can try some examples:
     ```bash
     source /opt/ros/foxy/setup.bash
     ros2 run demo_nodes_cpp talker

     source /opt/ros/foxy/setup.bash
     ros2 run demo_nodes_py listener
     ```
   ![image](https://github.com/GDHadeel/ROS-Noetic-ROS2-Foxy-on-Ubuntu-20.04/assets/126657301/77a290d1-5b59-41e4-970b-2ce1c2381e19)

---

## Acknowledgements
https://www.wikihow.com/Install-Ubuntu-on-VirtualBox
https://wiki.ros.org/noetic/Installation/Ubuntu
https://docs.ros.org/en/foxy/Installation/Ubuntu-Install-Debians.html#id7
https://www.youtube.com/watch?v=09giO7_UrB4&list=PLvG04RqmBajDdTTFSdMC9Wi4duqejaKu1&index=4&t=2747s

