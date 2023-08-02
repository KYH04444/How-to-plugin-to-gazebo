# How-to-plugin-to-gazebo

Models configuration (based on PX4)
1. Create a folder under Tools/simulation/gazebo/sitl_gazebo/models: car
2. Create the files under Tools/simulation/gazebo/sitl_gazebo/models/car: model.config and car.sdf and meshes and urdf files
3. Tools/simulation/gazebo/sitl_gazebo/worlds: grass_pad
4. Create an airframe file under ROMFS/px4fmu_common/init.d-posix/airframes
5. Add the airframe file, for example 1076_gazebo-classic_car to ROMFS/px4fmu_common/init.d-posix/airframes/CMakeLists.txt at the bottom of the list starting with px4_add_romfs_files(...
6. Add the airframe name (car) to the file src/modules/simulation/simulator_mavlink/sitl_targets_gazebo.cmake in the command that starts with set(models … as-well as the world file grass_pad to the line starting with set(worlds...
7. Add the models file to .gazebo/models

models, world는 launch file의 include를 통해 plugin
