# ROS-Noetic-ROS2-Foxy-on-Ubuntu-20.04 

## Description
This repository provides detailed guidelines for installing ROS Noetic and ROS2 Foxy on Ubuntu 20.04. By following these steps, you can establish a robust development environment for your robotics projects.

### Prerequisites

* Download Ubuntu 20.04 desktop image from [here](https://releases.ubuntu.com/20.04/)..
* Open VirtualBox and create a new virtual machine.
* Follow this [guide](https://www.wikihow.com/Install-Ubuntu-on-VirtualBox) to install Ubuntu 20.04 on VirtualBox.

---

### Install ROS Noetic

#### Ubuntu 20.04 on VirtualBox
If you haven't already, start by installing Ubuntu 20.04 on VirtualBox. Here's how:

1. **Download Ubuntu 20.04 ISO:**
   - Visit the [Ubuntu download page](https://ubuntu.com/download/desktop) and download the Ubuntu 20.04 LTS ISO file.

2. **Create a Virtual Machine in VirtualBox:**
   - Open VirtualBox and click on "New" to create a new virtual machine.
   - Follow the wizard to set up the virtual machine, allocating memory and creating a virtual hard disk.

3. **Install Ubuntu 20.04:**
   - Select the Ubuntu 20.04 ISO file as the startup disk for the virtual machine.
   - Follow the on-screen instructions to install Ubuntu 20.04 within the virtual machine.

4. **Open Terminal:**
   - Once Ubuntu 20.04 is installed and booted up, open a terminal window (`Ctrl + Alt + T`).

#### Install ROS Noetic

Now, let's install ROS Noetic:

1. **Setup your sources.list:**
   - Open a terminal and enter the following command to set up your sources list:
     ```bash
     sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
     ```

2. **Set up your keys:**
   - ```bash
     curl -fsSL https://www.robotis.com/docs/ROS/source.list.ros.txt | sudo tee /etc/apt/sources.list.d/ros-latest.list
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
