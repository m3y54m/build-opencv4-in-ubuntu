# Build OpenCV 4 in Ubuntu

Instructions to build OpenCV 4 from source in Ubuntu 20.04

https://docs.opencv.org/4.5.3/d7/d9f/tutorial_linux_install.html

## Check OS version

```console
uname -a
```

The result:

```
Linux my-computer-name 5.11.0-37-generic #41~20.04.2-Ubuntu SMP Fri Sep 24 09:06:38 UTC 2021 x86_64 x86_64 x86_64 GNU/Linux
```

## Download latest version of OpenCV 4 from GitHub

Core modules:

```console
wget -O https://github.com/opencv/opencv/archive/refs/tags/4.5.3.tar.gz
```
Extra modules:

```console
wget -O https://github.com/opencv/opencv_contrib/archive/refs/tags/4.5.3.tar.gz
```

## Extract the source

```console
tar -xzf opencv-4.5.3.tar.gz
tar -xzf opencv_contrib-4.5.3.tar.gz 
```

## Create build directory

```console
mkdir -p build
cd build
```

## Install minimal prerequisites

```console
sudo apt update && sudo apt install -y cmake g++ wget
```

## Configure

```console
cmake -DOPENCV_EXTRA_MODULES_PATH=../opencv_contrib-4.5.3/modules ../opencv-4.5.3
```

## Build

```console
make -j8
```

## Install

```console
sudo make install
```
