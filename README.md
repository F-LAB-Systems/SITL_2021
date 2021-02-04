# SITL_2021
This documentation will guide you on how to set up a SITL (Software in the loop) on UBUNTU 20.04 LTS with PX4-Autopilot, QGroundControl paired with simulation software Gazebo 11.
Author - @Anup1410

![F-lab](https://user-images.githubusercontent.com/78522341/106847388-cc341f80-66d4-11eb-9966-00c068135fcc.png)

Let's get started by opening up the Terminal on you system and following the commands

## STEP 1

```
cd ~
git clone https://github.com/PX4/PX4-Autopilot.git --recursive
bash ./Tools/setup/ubuntu.sh
```
## Step 2

```
cd ~
curl -sSL http://get.gazebosim.org | sh
```
Visit <a href="http://gazebosim.org/tutorials?tut=install_ubuntu">Gazebo</a> website for Alternative installation

## Step 3

Now cd into the PX4-Autopilot directory
```
cd PX4-Autopilot
make px4_sitl gazebo //QuadCopter
```
You can visit <a href="https://docs.px4.io/master/en/simulation/gazebo.html">PX4</a> website for more models

The terminal may prompt you to install some python modules during this installation.
for example
```
pip3 install --user empy
pip3 install --user toml
pip3 install --user numpy
pip3 install --user jinja2
```
If you still get error and are not propmted to install any more dependencies install Gstreamer

```
sudo apt install libgstreamer1.0-dev
sudo apt install gstreamer1.0-plugins-good
sudo apt install gstreamer1.0-plugins-bad
sudo apt install gstreamer1.0-plugins-ugly
```
## Step 4 

QGoundControl Installation

1. Before installing QGroundControl
   Enter the following in Terminal

```
sudo usermod -a -G dialout $USER
sudo apt-get remove modemmanager -y
sudo apt install gstreamer1.0-plugins-bad gstreamer1.0-libav gstreamer1.0-gl -y
```
2. Logout and login again to enable the change to user permissions on your Ubuntu Machine

3. Download <a href="https://s3-us-west-2.amazonaws.com/qgroundcontrol/latest/QGroundControl.AppImage">QGroundControl</a>

4. cd into the folder where QGroundControl was downloaded and execute this commands

```
cd ~
cd Documents
chmod +x ./QGroundControl.AppImage
./QGroundControl.AppImage  (or double click onto the file in documents)
```
