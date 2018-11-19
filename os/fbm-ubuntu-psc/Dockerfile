FROM ubuntu:16.04

# KEEP UP TO DATE
RUN apt-get -y update && apt-get -y upgrade 
# && apt-get -y dist-upgrade && apt-get -y autoremove

# Interpreter and the package manager
RUN apt-get -y install python3 python3-pip

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
RUN pip3 install scikit-learn
# RUN apt-get -y install libatlas3gf-base 

# INSTALL AN IDE FOR PYTHON with autocomplete
RUN apt-get -y install spyder3
RUN pip3 install rope_py3k
RUN pip3 install --upgrade pip

# Settings
RUN pip3 install -U numpy

# OpenCV-Python
RUN apt-get install -y python-opencv
RUN pip3 install opencv-python
RUN pip3 install -U imutils

# Tools
RUN apt-get install -y nano
RUN apt-get install -y net-tools
RUN apt-get install -y x11-xserver-utils
RUN apt-get install -y inetutils-ping telnet 

# Pre-requisites DLIB
RUN apt-get install -y build-essential cmake
RUN apt-get install -y libopenblas-dev liblapack-dev 
RUN apt-get install -y libx11-dev 
RUN apt-get update
RUN apt-get install -y libgtk-3-dev
RUN apt-get install -y python3-dev
RUN pip3 install dlib

# Faces Recognition
RUN pip3 install face_recognition
RUN pip3 install flask
RUN pip3 install requests
RUN pip3 install grequests