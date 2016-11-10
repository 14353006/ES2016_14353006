##安装ROS##
###安装过程（参考Ubuntu install of ROS Jade）
1. **Setup your sources.list**
	- Setup your computer to accept software from packages.ros.org. ROS Jade ONLY supports Trusty (14.04), Utopic (14.10) and Vivid (15.04) for debian packages
		- **CODE:** *sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'*
2. **Set up your key**
	- **CODE:** *sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net:80 --recv-key 0xB01FA116*
3. **Installation**
	- First, make sure your Debian package index is up-to-date
		- **CODE:** *sudo apt-get update*
	- There are many different libraries and tools in ROS. Using "Desktop-Full Install"
		- **CODE:** *sudo apt-get install ros-jade-desktop-full*
4. **Initialize rosdep**
	- Before you can use ROS, you will need to initialize rosdep. rosdep enables you to easily install system dependencies for source you want to compile and is required to run some core components in ROS
		- **CODE:** *sudo rosdep init*
		- **CODE:** *rosdep update*
5. **Environment setup**
	- It's convenient if the ROS environment variables are automatically added to your bash session every time a new shell is launched:
		- **CODE:** *echo "source /opt/ros/jade/setup.bash" >> ~/.bashrc*
		- **CODE:** *source ~/.bashrc*
6. **Getting rosinstall**
	- rosinstall is a frequently used command-line tool in ROS that is distributed separately. It enables you to easily download many source trees for ROS packages with one command.
		- **CODE:** *sudo apt-get install python-rosinstall*
7. **Obtain source code of the installed packages**
	- **CODE:** *apt-get source ros-jade-laser-pipeline*
###实验感想###
此次实验较为简单，理论上遵照网站上的指示一步步操作即可，同时由于此次实验也只是简单的安装，没有太多的验证结果，所以比较遗憾没有什么配图，进行最后一步操作后得到结果如下
![picture1](http://a1.qpic.cn/psb?/V11wIoXg0U0Il1/2NA0KjnehocxOBqCrzhjGE4BUUl9s4uDSoxzC26H0Us!/m/dOQAAAAAAAAAnull&bo=TgJKAAAAAAADByQ!&rf=photolist&t=5)
但是最后没有找到对应的package，尝试了*apt-cache search ros-jade-laser-pipeline*和*sudo apt-get install ros-jade-laser-pipeline*,确认了其已存在但是就是无法获得其源码（Unable to find a source package for xxx），之后我也尝试了一下其他的package，发现是同样的情况，鉴于目前对于ROS还不是太了解，暂时还没解决，之后再继续努力。
