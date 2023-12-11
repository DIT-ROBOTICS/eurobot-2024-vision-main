# <div align="center"> eurobot-2024-vision-main </div>
Vision Team utilizes 14 Intel RealSense cameras, distributed across courtside and onboard modules, to perform various detection tasks in Eurobot 2024.

<div align="center">
  <p>
    <a href="https://www.eurobot.org/eurobot-contest/eurobot-2024/" target="_blank">
      <img width="100%" src="https://github.com/pomelo925/pomelo925-resources/blob/main/eurobot-2024/eurobot-2024-map.png?raw=true" alt="eurobot-2024-map"></a>
  </p>
</div>

## <div align="center"> 🛠️ Getting Started 🛠️</div>

1. Clone this repository.
   
   ```bash
   git clone https://github.com/DIT-ROBOTICS/eurobot-2024-vision-main
   ```
3. Navigate to `eurobot-2024-vision-main` to initialize submodules.
   
   ```bash
   cd eurobot-2024-vision-main
   git submodule update --init
   ```
5. Follow the setup instructions within each submodule's README for detailed environment setup and dependencies installation.

## <div align="center"> 📷 Camera Configuration 📷</div>

### Courtside Cameras (2x4)

> 2 pairs, totaling 8 cameras, positioned strategically around the central and fixed beacons.

* 3 cameras monitor the central beacon (CB).
* 1 camera is specialized for detecting solar panel rotation on the fixed beacon (FB).

### Onboard Cameras (2+4)

> Both robots perform the same tasks but implement different technical details.

* 2 cameras mounted on a differential wheel system robot.
* 4 cameras mounted on a mecanum wheel system robot.

## <div align="center"> Vision Tasks and Technologies </div>

<div align="center">
    <p>
        <a href="https://github.com/ultralytics/ultralytics" target="_blank">
            <img width="51.5%" src="https://github.com/pomelo925/pomelo925-resources/blob/main/eurobot-2024/YOLOv8.png?raw=true" alt="eurobot-2024-map">
        </a>
        <a href="https://docs.opencv.org/4.x/d5/dae/tutorial_aruco_detection.html" target="_blank">
            <img width="44%" style="margin-right:20px;" src="https://github.com/pomelo925/pomelo925-resources/blob/main/eurobot-2024/arucotag.png?raw=true" alt="aruco-tag">
        </a>
    </p>
</div>

| Module    | Task                                  | Technology                                       |
|-----------|---------------------------------------|--------------------------------------------------|
| Courtside | Detect solar panel rotating angle     | Aruco tag                                        |
| Courtside | Detect position of plants and pots    | YOLOv8                                           |
| Onboard   | Precise position of plants and pots   | YOLOv8                                           |
| Onboard   | Detect ladybugs                       | Integration x depth    |


## <div align="center"> Contribution </div>

To contribute to the eurobot-2024-vision-main project, please refer to the CONTRIBUTING.md file for guidelines.

[![GitHub Avatar](https://github.com/pomelo925.png?size=50)](https://github.com/pomelo925) 

## <div align="center"> Support </div>

For any issues or support, please open an issue in this repository or contact the maintainers directly.
