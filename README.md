# moveit-tutorial-melodic
Stuff to get the moveit tutorial melodic running

Docker is a prerequisite.

Build the image,
```sh
$ cd docker_image
$ docker build -t moveit-tutorial .
```

Run the image,
```sh
$ cd ..
$ xhost +local:root
$ docker run --name moveit_tutorial_app -it --rm --net=host --privileged -e DISPLAY=$DISPLAY -v /tmp/.X11-unix/:/tmp/.X11-unix -v $(pwd):/root moveit-tutorial
$ cd root/ws_moveit
$ source /opt/ros/melodic/setup.bash
$ catkin_make
$ source devel/setup.bash
```

And you are good to go!


Example of running pick and place demo

```sh
$ roslaunch panda_moveit_config demo.launch
```

Open new terminal,
```sh
$ docker exec -it moveit_tutorial_app /bin/bash
$ cd root/ws_moveit
$ source devel/setup.bash
$ rosrun moveit_tutorials pick_place_tutorial
```






 






