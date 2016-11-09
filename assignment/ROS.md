#Ubuntu 16.04 ROS的安装配置
---------------------------------  
<p>1. 设置sources.list </p> 
<pre><code>
$ sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu   
$ (lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
</code></pre>
<p>2.设置keys</p>
<pre><code>
$ sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net:80 --recv-key 0xB01FA116
</code></pre>
![keys](http://a1.qpic.cn/psb?/V10xhQuy3m7suY/6MmzNB*HvWhc7KTkAAAh3U7HxbfDZvetDz4U379VBIA!/b/dHcBAAAAAAAA&bo=2AOvAAAAAAADB1Y!&rf=viewer_4)
<p>3.安装:</p> 
<p>①桌面安装：ROS，rqt，rviz和robot通用库</p>
<p>②安装特定的ROS包</p>
<pre><code>
$ sudo apt-get update
$ sudo apt-get install ros-kinetic-desktop-full
$ sudo apt-get install ros-kinetic-desktop
$ sudo apt-get install ros-kinetic-ros-base
$ sudo apt-get install ros-kinetic-PACKAGE
</code></pre>
<p>4.初始化rosdep</p>
<pre><code>
$ sudo rosdep init
$ rosdep update
</code></pre>
![Initialize](http://a1.qpic.cn/psb?/V10xhQuy3m7suY/Oa*pkW3danPebSt1Jq*fRzuxbmGaMW0uy6O2r8Bvi78!/b/dHEBAAAAAAAA&bo=EwNYAQAAAAADB2s!&rf=viewer_4)
<p>5.环境配置(可用两种方法配置改变环境)</p>
<pre><code>
$ echo "source /opt/ros/kinetic/setup.bash" >> ~/.bashrc
$ source ~/.bashrc
$ source /opt/ros/kinetic/setup.bash
</code></pre>
<p>6.获取rosinstall</p>
<pre><code>
$ sudo apt-get install python-rosinstall
</code></pre>
<p>7.测试</p>
<pre><code>
$ roscore
</code></pre>
**新建Terminal,输入下述命令.开启一个小海龟界面**  
<pre><code>
$ rosrun turtlesim turtlesim_node 
</code></pre>
**再打开一个Terminal,输入下述命令**
<pre><code>
$ rosrun turtlesim turtle_teleop_key 
</code></pre>
**键盘按方向键,可控制小乌龟移动**
![小乌龟](http://a2.qpic.cn/psb?/V10xhQuy3m7suY/vdtoGTJ4wMCL3YXqUzRsxweki9v04wxblsxCwhRRuvo!/b/dAkBAAAAAAAA&bo=DwVNAgAAAAADB2c!&rf=viewer_4)
**再打开一个Terminal,输入命令,可以看到当前ROS nodes以及Topic等图形展示**
<pre><code>
$ rosrun rqt_graph rqt_graph 
</code></code>
![图形](http://a1.qpic.cn/psb?/V10xhQuy3m7suY/5nF4m3rAJKQDRQpEyvdar71xceUUoexEAzspCKj4aeo!/b/dAsBAAAAAAAA&bo=dAPZAQAAAAADB40!&rf=viewer_4)
