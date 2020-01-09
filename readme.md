# 树莓派搭建opencv 4.1.0

```shell
sudo raspi-config

raspivid -t 0 -cs 0

摄像头设备文件为/dev/video0

sudo nano /etc/modules
bcm2835-v4l2

/etc/apt/sources.list
deb http://mirrors.tuna.tsinghua.edu.cn/raspbian/raspbian/ buster main non-free contrib
deb-src http://mirrors.tuna.tsinghua.edu.cn/raspbian/raspbian/ buster main non-free contrib

/etc/apt/sources.list.d/raspi.list
deb http://mirrors.tuna.tsinghua.edu.cn/raspberrypi/ buster main ui


#pip install pip -U
pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple


sudo reboot

sudo pip3 install numpy

sudo apt-get install build-essential git cmake pkg-config -y
sudo apt-get install libjpeg8-dev -y
sudo apt-get install libtiff5-dev -y
sudo apt-get install libjasper-dev -y
sudo apt-get install libpng12-dev -y

sudo apt-get install libavcodec-dev libavformat-dev libswscale-dev libv4l-dev -y

sudo apt-get install libgtk2.0-dev -y
sudo apt-get install libatlas-base-dev gfortran -y


copy 2files to /home/pi and unzip file




cd /home/pi/Downloads/opencv-4.1.0
mkdir build
cd build


cmake -D CMAKE_BUILD_TYPE=RELEASE \
-D CMAKE_INSTALL_PREFIX=/usr/local \
-D INSTALL_C_EXAMPLES=ON \
-D INSTALL_PYTHON_EXAMPLES=ON \
-D OPENCV_EXTRA_MODULES_PATH=/home/pi/opencv_contrib-4.1.0/modules \
-D BUILD_EXAMPLES=ON \
-D WITH_LIBV4L=ON \
-D PYTHON3_EXECUTABLE=/usr/bin/python3.7 \
-D PYTHON_INCLUDE_DIR=/usr/include/python3.7 \
-D PYTHON_LIBRARY=/usr/lib/arm-linux-gnueabihf/libpython3.7m.so \
-D PYTHON3_NUMPY_INCLUDE_DIRS=/usr/lib/python3/dist-packages/numpy/core/include \
..

make

sudo make install










```

