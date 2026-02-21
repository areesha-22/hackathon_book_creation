---
sidebar_position: 1
title: "Introduction to ROS 2 Architecture"
---

# Introduction to ROS 2 Architecture

## Overview

ROS 2 (Robot Operating System 2) is a flexible framework for writing robot software. It is a collection of tools, libraries, and conventions that aim to simplify the task of creating complex and robust robot behavior across a wide variety of robot platforms.

## Key Concepts

### Nodes
Nodes are the fundamental building blocks of ROS 2 applications. They are processes that perform computation and communicate with other nodes through messages.

### Topics
Topics are named buses over which nodes exchange messages. They provide a way for nodes to publish and subscribe to data streams.

### Services
Services provide a request/reply communication pattern between nodes, allowing for synchronous communication.

### Actions
Actions are goal-oriented communication patterns that include feedback and status information.

## Architecture Components

### DDS (Data Distribution Service)
ROS 2 uses DDS as its underlying middleware. DDS provides the infrastructure for discovery, data distribution, and quality of service policies.

### RMW (ROS Middleware)
The ROS Middleware layer abstracts the underlying DDS implementation, allowing ROS 2 to work with different DDS vendors.

### Quality of Service (QoS)
QoS settings allow fine-tuning of communication behavior, including reliability, durability, and liveliness policies.