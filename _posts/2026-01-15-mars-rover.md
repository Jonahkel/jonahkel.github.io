---
title: "Mars Rover: Autonomous Navigation"
date: 2026-01-15 12:00:00 +0000
categories: [Software, Robotics]
tags: [cpp, ros2, python]
description: "Developing a robust navigation stack using ROS2, Python, and C++ to enable autonomous traversal of difficult terrain for the Michigan Mars Rover."
image:
  path: /assets/rover.png
  alt: "The Michigan Mars Rover navigating a rocky terrain."
---

From Sepetember 2024 to May 2025, I was an autonomy software programmer for the Michigan Mars Rover team. My work focused on enabling the rover to traverse rugged, unknown terrain using real-time environmental sensing pathfinding. All software was developed in ROS2 (Robotic Operating System 2), a popular framework for robotics software development. I mostly programmed using both C++ and Python, taking advantage of its ROS2's tools for visualization, simulation, and logging.

One of my goals was to write software for the rover's robotic arm. A recent addition to the competition, the rover would use the arm to type commands on a physical keyboard. Using RViz (ROS Visualization), I designed a high-fidelity point cloud model that mapped the arm's exact operational workspace. This spatial analysis was critical for the path-planning algorithm, ensuring that every coordinate instruction sent was within the arm's physical reach, thereby preventing hardware strain and execution failures during the competition.

![Robotic Arm Reachability Model](/assets/pointcloud.png)
_Figure 1: RViz visualization of the 3D point cloud used to model the robotic arm's operational workspace._

I also worked extensively on the navigation software. During the competition, our rover was to autonomously detect, move toward, and retrieve various objects placed around the environment. I focused mainly on the pathfinding aspect. First, I refined the search algorithm using A* to dynamically find the best path around rocks and other obstacles. Later, I grappled with several edge cases behaviors when the rover was required to go near unreachable terrain. For instance, the rover would sometimes need to move near a rock to pick up a nearby water bottle. I designed an algorithm that dynamically adjusted the rover's safety buffers. By assigning a lower penalty to high-risk zones when a target was within proximity, I enabled the rover to execute precision maneuvers in tight spaces without compromising the overall safety of the rover.

![ROS Navigation Costmap](/assets/rover_path.png)
_Figure 2: RViz visualization of the navigation costmap._

My time on the Mars Rover team was overall a great experience for me. It was really fun to work with other students on a robotics project again. (Fun fact: my first programming experience, which inspired me to study computer science, was a robotics course in high school.) ROS2 is a very useful, albeit often frustrating, robotics framework, which I'm glad I learned. The Mars Rover team also gave me experience collaborating with several other software engineers on a complex codebase, and I became proficient with Git techniques such as creating/solving issues, pull requests, and merging branches.
