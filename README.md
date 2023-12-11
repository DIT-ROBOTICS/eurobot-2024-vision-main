# <div align="center"> eurobot-2024-vision-main </div>
Vision Team utilizes 14 Intel RealSense cameras, distributed across courtside and onboard modules, to perform various detection tasks in Eurobot 2024.

## <div align="center"> Getting Started </div>
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

## <div align="center"> Camera Configuration </div>
### Courtside Cameras (2x4)
> 2 pairs, totaling 8 cameras, positioned strategically around the central and fixed beacons.
* 3 cameras monitor the central beacon (CB).
* 1 camera is specialized for detecting solar panel rotation on the fixed beacon (FB).

### Onboard Cameras (2+4)
> Both robots perform the same tasks but implement different technical details.
* 2 cameras mounted on a differential wheel system robot.
* 4 cameras mounted on a mecanum wheel system robot.

## <div align="center"> Vision Tasks and Technologies </div>

| Module    | Task                                  | Technology                                       |
|-----------|---------------------------------------|--------------------------------------------------|
| Courtside | Detect solar panel rotating angle     | Aruco tag                                        |
| Courtside | Detect position of plants and pots    | YOLOv8                                           |
| Onboard   | Precise position of plants and pots   | YOLOv8                                           |
| Onboard   | Detect ladybugs                       | Integration x depth    |

## <div align="center"> Contribution </div>

We love your input! 
To contribute to the eurobot-2024-vision-main project, please refer to the CONTRIBUTING.md file for guidelines.

## <div align="center"> Support </div>
For any issues or support, please open an issue in this repository or contact the maintainers directly.
