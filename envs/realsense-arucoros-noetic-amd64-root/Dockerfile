## ARM64 architecture ##
FROM ros:noetic 

LABEL org.opencontainers.image.authors="yoseph.huang@gmail.com"

## pkgs installation
RUN apt-get update && apt-get install -y \
    sudo net-tools ssh nano git usbutils x11-apps \
    apt-utils ros-noetic-tf* \
    libssl-dev libusb-1.0-0-dev libudev-dev pkg-config udev \
    libx11-dev libxrandr-dev libxinerama-dev libxcursor-dev \
    libglu1-mesa-dev libglew-dev mesa-common-dev libxi-dev \
    ros-noetic-diagnostic-updater ros-noetic-rviz \
    && rm -rf /var/lib/apt/lists/*d

### install realsense SDK
WORKDIR /home
RUN git clone https://github.com/IntelRealSense/librealsense.git /opt/librealsense
WORKDIR /opt/librealsense/build
RUN cmake ../ -DBUILD_EXAMPLES=true -DCMAKE_BUILD_TYPE=Release && \
    make -j4 && make install


### ros pkg
WORKDIR /home/realsense-ws/src
RUN git clone -b noetic-devel https://github.com/pal-robotics/aruco_ros.git && \
    git clone --branch 0.3.7 https://github.com/ros-drivers/usb_cam.git && \
    git clone https://github.com/ros-perception/image_pipeline.git && \
    git clone https://github.com/pal-robotics/ddynamic_reconfigure.git && \
    git clone --branch ros1-legacy --single-branch https://github.com/IntelRealSense/realsense-ros.git && \
    (cd realsense-ros && git checkout $(git tag | sort -V | grep -P "^2.\\d+\\.\\d+" | tail -1))

### install and build dependencies
RUN sudo apt-get update && \
    rosdep update && \
    rosdep install --from-paths . --ignore-src -r -y && \
    cd .. && \
    /bin/bash -c 'source /opt/ros/$ROS_DISTRO/setup.bash; catkin_make' && \
    echo "source /opt/ros/$ROS_DISTRO/setup.bash" >> ~/.bashrc \
    && sudo rm -rf /var/lib/apt/lists/* 

CMD ["/bin/bash"]
