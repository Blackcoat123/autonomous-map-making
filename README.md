
# 🧱 Custom Maze Navigation with TurtleBot3 in Gazebo

This project demonstrates how to use **TurtleBot3** with **ROS 2**, **Gazebo**, **SLAM**, and **navigation** to autonomously explore a custom maze environment. Below are the step-by-step instructions to set up and run the simulation.

## ✅ Prerequisites

- ROS 2 (e.g. Humble or later) installed and sourced.
- TurtleBot3 packages installed:
  - `turtlebot3`
  - `turtlebot3_simulations`
  - `nav2_bringup`
  - `slam_toolbox`
  - `explore_lite`
- Gazebo simulator installed and working.
- Set the environment variable:

```bash
export TURTLEBOT3_MODEL=burger
```

---

## 🚀 Step 1 – Launch the Custom Maze World

Start Gazebo with your custom map (maze environment) and spawn the TurtleBot3 robot.

```bash
ros2 launch turtlebot3_gazebo world1.launch.py
```

✔ This will open Gazebo and load your custom world along with the robot at a predefined location.

---

## 🚀 Step 2 – Start Navigation Stack

Bring up the Navigation2 stack to allow path planning and obstacle avoidance.

```bash
ros2 launch nav2_bringup navigation_launch.py
```

✔ This enables autonomous navigation, allowing the robot to plan and follow paths to goal points in the environment.

---

## 🚀 Step 3 – Start SLAM for Mapping

Run SLAM (Simultaneous Localization and Mapping) to dynamically build the map as the robot explores.

```bash
ros2 launch slam_toolbox online_async_launch.py
```

✔ The robot will start mapping the environment while keeping track of its position.

---

## 🚀 Step 4 – Visualize in RViz

Launch RViz to visualize the robot, map, sensor data, and navigation paths in real-time.

```bash
rviz2
```

✔ Use RViz to debug and monitor the robot’s pose, sensors, and navigation.

---

## 🚀 Step 5 – Enable Autonomous Exploration

Start exploration using the `explore_lite` package. The robot will autonomously explore the environment and build the map.

```bash
ros2 launch explore_lite explore.launch.py
```

✔ The robot will roam around, avoid obstacles, and explore unknown areas efficiently.

---

## 📚 Additional Notes

- ✅ **Order Matters**: Launch Gazebo → Navigation → SLAM → RViz → Exploration.
- ✅ **SLAM vs Navigation**: SLAM builds the map while Navigation plans paths on that map.
- ✅ **RViz is Essential**: Visualize the robot’s pose, sensor data, and navigation goals.
- ✅ **Set Environment Variable**: Ensure `TURTLEBOT3_MODEL=burger` is set before running commands.
- ✅ **Custom Maps**: You can design mazes with corridors and obstacles for testing navigation algorithms.
- ✅ **Logging & Debugging**: Use terminal outputs and RViz to monitor behavior and diagnose issues.
- ✅ **Extendibility**: Integrate AI, reinforcement learning, or extra sensors for advanced robotics projects.

---

## 📂 Suggested File Structure

```
.
├── maps/
│   └── maze_world.world
├── launch/
│   ├── world1.launch.py
│   ├── navigation_launch.py
│   ├── online_async_launch.py
│   └── explore.launch.py
├── config/
│   ├── nav2_params.yaml
│   └── slam_toolbox_params.yaml
└── README.md
```

---

## 🎯 Learnings from this Setup

- Integration of **SLAM** and **Navigation** with TurtleBot3.
- Real-time sensor data processing using **Lidar** and **IMU**.
- Building maps of unknown environments using **online SLAM**.
- Autonomous exploration strategies with **explore_lite**.
- Visualization and debugging using **RViz**.
- Structuring ROS 2 projects for scalability and collaboration.

---

## 📌 Tips for Further Development

- ✅ Tune SLAM parameters like map resolution and update rate for better accuracy.
- ✅ Experiment with different exploration algorithms and obstacle avoidance strategies.
- ✅ Integrate with AI frameworks for path optimization or adaptive exploration.
- ✅ Use recording tools like `rosbag` to capture sessions for offline analysis.
- ✅ Add logging and monitoring dashboards to track performance and errors.

---

Feel free to explore, experiment, and expand this setup to build advanced robotics applications!
