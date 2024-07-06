# ROS-Noetic-ROS2-Foxy-on-Ubuntu-20.04 

## Description
This repository provides detailed guidelines for installing ROS Noetic and ROS2 Foxy on Ubuntu 20.04. By following these steps, you can establish a robust development environment for your robotics projects.

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

* Now, let's install ROS Noetic:

1. **Setup your sources.list:**
   - Open a terminal and enter the following command to set up your sources list:
     ```bash
     sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
     ```

2. **Set up your keys:**
   - ```bash
     sudo apt install curl # if you haven't already installed curl
     curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
     ```
3. **Installation:**
   - First, make sure your Debian package index is up-to-date:
   - ```bash
     sudo apt update
     ```

4. **Desktop-Full Install: (Recommended) :**
   - ```bash
     sudo apt install ros-noetic-desktop-full
     ```
5. **Environment setup:**
   - You must source this script in every bash terminal you use ROS in.
   - ```bash
     source /opt/ros/noetic/setup.bash
     ```
     
6. **Environment setup:**
   - To install this tool and other dependencies for building ROS packages, run:
   - ```bash
     sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential
     ```
     
   - Initialize rosdep
   - ```bash
     sudo apt install python3-rosdep
     ```

   - With the following, you can initialize rosdep.
   - ```bash
     sudo rosdep init
     rosdep update
     ```


---

### Install ROS2 Foxy

#### Install ROS2 Foxy
Follow these steps to install ROS2 Foxy on Ubuntu 20.04:

1. **Setup your sources.list:**
   - Add the ROS 2 repository to your sources list:
     ```bash
     sudo sh -c 'echo "deb http://packages.ros.org/ros2/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros2-latest.list'
     ```

2. **Set up your keys:**
   - ```bash
     curl -fsSL https://www.robotis.com/docs/ROS/source.list.ros.txt | sudo tee /etc/apt/sources.list.d/ros-latest.list
     ```

3. **Install ROS2 packages:**
   - Update your package index and install ROS 2 packages:
     ```bash
     sudo apt update
     sudo apt install ros-foxy-desktop
     ```

---

### Verify Installation

After completing the installations, verify that ROS Noetic and ROS2 Foxy are correctly installed:

1. **Source ROS setup files:**
   - Source the ROS setup files in your current terminal session:
     ```bash
     source /opt/ros/noetic/setup.bash   # For ROS Noetic
     source /opt/ros/foxy/setup.bash     # For ROS2 Foxy
     ```

2. **Check ROS version:**
   - Verify the ROS installation by checking the version:
     ```bash
     rosversion -d   # For ROS Noetic
     ros2 --version  # For ROS2 Foxy
     ```

3. **Test Installation:**
   - Run a sample ROS or ROS2 command to ensure everything is working:
     ```bash
     roscore           # For ROS Noetic
     ros2 run demo_nodes_cpp talker     # For ROS2 Foxy
     ```

---

These steps will guide you through setting up ROS Noetic and ROS2 Foxy on Ubuntu 20.04 using VirtualBox. Adjust paths and commands as needed for your specific setup.
