# A Fork of Fork of openpilot

original fork https://github.com/ShaneSmiskol/openpilot/, only tested in car corolla 2020

## Additional Features

### output all op internal data structure over WIFI for my HMI prototype
[![](https://img.youtube.com/vi/rxTK5McUPA4/0.jpg)](https://www.youtube.com/watch?v=rxTK5McUPA4)

### automaticlly adjust in lane offset
It will check if the ego car is in the left most lane or right most lane or middle lane,
if ego is in left most lane, it will adjust the offset 0.2m to the left and vice versa to keep distance away from the big truck.
Sometimes the car is driving too much "dead center", human driver wont do that


![pic1](./doc/lateral_offset.png?raw=true)

keep left (0.2m) if you have cars on your right side
![keep_left](./doc/keep_left.jpg?raw=true)

keep center is there is no car surrounded
![keep_center](./doc/keep_center.jpg?raw=true)

### offline simulation testing tool
Instead of carla, we use a simple python script to simulate in car environment with mock can messages

``` sh
ssh to C2
cd /data/openpilot
./selfdrive/golden/can_bridge.py # start simulation
```

you can copy these scripts
[can_bridge.py](../blob/stock_additions_new/selfdrive/golden/can_bridge.py)
[can.py](../blob/stock_additions_new/selfdrive/golden/can.py)
[keyboard_ctrl.py](../blob/stock_additions_new/selfdrive/golden/keyboard_ctrl.py)

to selfdrive/golden/ folder with you own repo without modifying any source code of openpilot

![pic2](./doc/sim_script.png?raw=true)

