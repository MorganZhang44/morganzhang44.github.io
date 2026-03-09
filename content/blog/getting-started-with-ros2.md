---
title: "Getting Started with ROS 2: A Practical Guide"
date: 2025-11-20
description: "A beginner-friendly introduction to building robotics applications with ROS 2 Humble."
tags: ["ROS 2", "Robotics", "Tutorial"]
categories: ["Tutorials"]
summary: "Learn the fundamentals of ROS 2 — workspaces, nodes, topics, and services — with hands-on examples you can run on any Ubuntu machine."
ShowToc: true
---

If you're getting into robotics software development, **ROS 2** (Robot Operating System 2) is the framework you'll encounter everywhere — from university labs to industry. This guide walks you through the essentials.

## Why ROS 2?

ROS 2 is the de-facto middleware for robotics. Compared to its predecessor:

- **Real-time capable** via DDS communication
- **Cross-platform** — works on Linux, macOS, and Windows
- **Production-ready** — designed for industrial and safety-critical systems
- **Active community** — thousands of packages and contributors

## Setting Up Your Workspace

First, install ROS 2 Humble on Ubuntu 22.04:

```bash
sudo apt update && sudo apt install ros-humble-desktop
source /opt/ros/humble/setup.bash
```

Create a workspace:

```bash
mkdir -p ~/ros2_ws/src
cd ~/ros2_ws
colcon build
source install/setup.bash
```

## Your First Node

Create a simple Python publisher:

```python
import rclpy
from rclpy.node import Node
from std_msgs.msg import String

class HelloPublisher(Node):
    def __init__(self):
        super().__init__('hello_publisher')
        self.publisher_ = self.create_publisher(String, 'hello_topic', 10)
        self.timer = self.create_timer(1.0, self.timer_callback)

    def timer_callback(self):
        msg = String()
        msg.data = 'Hello, ROS 2!'
        self.publisher_.publish(msg)
        self.get_logger().info(f'Published: {msg.data}')

def main():
    rclpy.init()
    node = HelloPublisher()
    rclpy.spin(node)
    node.destroy_node()
    rclpy.shutdown()
```

## Key Concepts

| Concept | Description |
|---|---|
| **Node** | An independent process that performs computation |
| **Topic** | A named bus for asynchronous message passing |
| **Service** | A synchronous request-response pattern |
| **Action** | Long-running tasks with feedback (e.g., navigation) |

## Next Steps

- Explore the [official ROS 2 tutorials](https://docs.ros.org/en/humble/Tutorials.html)
- Try `turtlesim` to visualize publisher/subscriber communication
- Build a custom message type for your robot project

---

*Have questions or suggestions? Drop me a line — I'd love to hear what you're building!*
