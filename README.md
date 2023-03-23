# yahboom_imu
yahboom's IMU driver.


## Usage
run node by roslaunch
```bash
roslaunch wit_ros_imu rviz_and_imu.launch
```

## Notice
- Change the boudrate if necessary. Otherwise, no output.
- The frequency is setted by window's software.
- Read the `.pdf` document for more details;

## Issues
In window's APP, set update-rate: "188Hz", output-rate: 100Hz, baudrate: 115200. Smaller update-rate can't reach output-rate.  
Select: acc, gryo, eular. Eular angle does not influence the output data quality, but can be shown in rviz, so reserved.  
In ros code, skip every 3 times in `handleSerialData`, since the buffer size is 33 data and published every 11 data. 