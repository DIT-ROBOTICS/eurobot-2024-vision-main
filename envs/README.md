# Intel® RealSense™ Multifaceted Toolkit

This repository serves as a gateway to harness the full potential of RealSense™ across a wide range of contexts and applications.

## A. Build Image and Run Container

The architecture of its each environment is  on the folder name.

1. Git clone this repo.

    ```bash
    git clone https://github.com/pomelo925/arucoros-realsense.git
    ```

2. Navigate to `/realsense-arucoros-noetic-arm64 page` (for example) and run the docker image.

    ```bash
    docker compose up
    ```

3. In Visual Studio Code, press `F1` to open the command palette.

4. Type and select Remote-Containers : "Attach to Running Container...".

5. Choose the container named `pomelo` from the list to enter container.

## B. Hardware Check

Make sure Intel® RealSense™ is detected by the host machine.

Type `lsusb` in the terminal, and it should show something like:

```bash
Bus 001 Device 004: ID 8086:0b3a Intel Corp. Intel(R) RealSense(TM) Depth Camera 435i
```

>`dmesg | grep tty` will NOT list oout RealSense™ cuz it interfaces with specialized drivers UVC (USB Video Class) provided by the Intel RealSense SDK.

## C. Intel® RealSense™ Connection Test

if error like this:

```bash
07/12 05:04:42,078 ERROR [281472812437904] (librealsense-exception.h:52) xioctl(VIDIOC_G_CTRL) failed Last Error: Connection timed out
 ```

please make sure Intel® RealSense™ is inserted on USB 3.0 port (with the blue mark).
