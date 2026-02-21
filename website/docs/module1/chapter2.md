---
sidebar_position: 2
title: "Python Integration with rclpy"
---

# Python Integration with rclpy

## Overview

rclpy is the Python client library for ROS 2. It provides a Python API that wraps around the underlying ROS 2 middleware, enabling Python developers to create ROS 2 nodes, publishers, subscribers, and services.

## Installation and Setup

To use rclpy, you need to have a ROS 2 installation. You can install rclpy via pip if you have ROS 2 sourced:

```bash
pip install rclpy
```

## Creating a Node

The basic structure of a ROS 2 node in Python includes importing rclpy, initializing it, creating a node, and spinning:

```python
import rclpy
from rclpy.node import Node

class MinimalPublisher(Node):
    def __init__(self):
        super().__init__('minimal_publisher')
        self.publisher_ = self.create_publisher(String, 'topic', 10)
        timer_period = 0.5  # seconds
        self.timer = self.create_timer(timer_period, self.timer_callback)
        self.i = 0

    def timer_callback(self):
        msg = String()
        msg.data = 'Hello World: %d' % self.i
        self.publisher_.publish(msg)
        self.get_logger().info('Publishing: "%s"' % msg.data)
        self.i += 1

def main(args=None):
    rclpy.init(args=args)
    minimal_publisher = MinimalPublisher()
    rclpy.spin(minimal_publisher)
    minimal_publisher.destroy_node()
    rclpy.shutdown()

if __name__ == '__main__':
    main()
```

## Publishers and Subscribers

### Publisher
A publisher sends messages to a topic. Multiple nodes can publish to the same topic.

### Subscriber
A subscriber receives messages from a topic. Multiple nodes can subscribe to the same topic.

## Services and Clients

Services provide a request-response communication pattern in ROS 2. A service server handles requests and returns responses to clients.