FROM ubuntu:16.04

RUN  apt-get update
RUN apt-get upgrade -y

# Remove any previous installations of x264</h3>
RUN apt-get remove x264 libx264-dev

# Install dependencies
RUN apt-get install -y build-essential checkinstall cmake pkg-config yasm
RUN apt-get install -y git gfortran
RUN apt-get install -y libjpeg8-dev libjasper-dev libpng12-dev

# Ubuntu 14.04
# RUN apt-get install libtiff4-dev
# Ubuntu 16.04
RUN apt-get install -y libtiff5-dev

# Require Dependencies
RUN apt-get install -y libavcodec-dev libavformat-dev libswscale-dev libdc1394-22-dev
RUN apt-get install -y libxine2-dev libv4l-dev
RUN apt-get install -y libgstreamer0.10-dev libgstreamer-plugins-base0.10-dev
RUN apt-get install -y qt5-default libgtk2.0-dev libtbb-dev
RUN apt-get install -y libatlas-base-dev
RUN apt-get install -y libfaac-dev libmp3lame-dev libtheora-dev
RUN apt-get install -y libvorbis-dev libxvidcore-dev
RUN apt-get install -y libopencore-amrnb-dev libopencore-amrwb-dev
RUN apt-get install -y x264 v4l-utils

# Optional dependencies
RUN apt-get install -y libprotobuf-dev protobuf-compiler
RUN apt-get install -y libgoogle-glog-dev libgflags-dev
RUN apt-get install -y libgphoto2-dev libeigen3-dev libhdf5-dev doxygen

# Install Python libraries
RUN apt-get install -y python-dev python-pip python3-dev python3-pip
RUN pip2 install -U pip numpy
RUN pip3 install -U pip numpy

# Download OpenCV and OpenCV_contrib
COPY ./opencv /home/fbm/opencv
COPY ./opencv_contrib /home/fbm/opencv_contrib

# Create a build directory
RUN mkdir /home/fbm/opencv/build
WORKDIR /home/fbm/opencv/build

# CMake
RUN cmake -D CMAKE_BUILD_TYPE=RELEASE \
      -D CMAKE_INSTALL_PREFIX="/usr/local" \
      -D INSTALL_C_EXAMPLES=ON \
      -D INSTALL_PYTHON_EXAMPLES=ON \
      -D WITH_TBB=ON \
      -D WITH_V4L=ON \
      -D WITH_QT=ON \
      -D WITH_OPENGL=ON \
      -D OPENCV_EXTRA_MODULES_PATH="/home/fbm/opencv_contrib/modules" \
      -D BUILD_EXAMPLES=ON /home/opencv/ ..

# Compile and Install ($ nproc - find out number of CPU cores in your machine)
RUN make -j4
RUN make install
RUN echo "/usr/local/lib" >> /etc/ld.so.conf.d/opencv.conf
RUN ldconfig

WORKDIR /home/fbm/
RUN apt-get -y update && apt-get -y upgrade

# XHOST
RUN apt-get install -y x11-xserver-utils

# Tools
RUN apt-get install -y inetutils-ping telnet 
RUN apt-get install -y net-tools
RUN apt-get install -y nano

# PYTHON DATA SCIENCE

# Essential scientific libraries
RUN apt-get -y install python3-numpy python3-matplotlib python3-scipy python3-pandas python3-simpy
# IPython
RUN apt-get -y install ipython3 ipython3-notebook
# OpenGL (Optional)
RUN apt-get -y install python3-opengl
# GUI development
RUN apt-get -y install python3-pyqt5 python3-pyqt5.qtopengl python3-pyqt5.qtquick
# Data storage
RUN apt-get -y install python3-h5py
# Computer vision
RUN apt-get -y install python3-skimage
RUN apt-get -y install libatlas-dev
# OpenCV-Python
RUN apt-get install -y python-opencv
# Pre-requisites DLIB
RUN apt-get install -y build-essential cmake
RUN apt-get install -y libopenblas-dev liblapack-dev 
RUN apt-get install -y libx11-dev 
RUN apt-get update
RUN apt-get install -y libgtk-3-dev
RUN apt-get install -y python3-dev

# Python Libs
RUN pip3 install scikit-learn
RUN pip3 install rope_py3k
RUN pip3 install opencv-python
RUN pip3 install dlib
RUN pip3 install imutils
RUN pip3 install face_recognition
RUN pip3 install flask
RUN pip3 install requests
RUN pip3 install grequests

