---

# 🎵 AI-Driven Music-Based Robot Choreography (ROS 2)

## Overview

This repository presents an **end-to-end AI pipeline for music-driven robot choreography**, where audio signals are transformed into synchronized robotic movements in real time. The system extracts musical features such as **tempo, beat timing, and loudness**, maps them to motion primitives, and executes coordinated dance actions on **Hiwonder JetRover robots** using **ROS 2**.

The project was developed as part of a university research and demonstration initiative and showcased in **live robot dance performances**.

---

## Key Features

* 🎧 Music-to-Motion pipeline (audio → features → motion)
* 🤖 ROS 2-based robot control (wheels + arm)
* 🕺 Beat-synchronized dance choreography
* ⚡ Real-time execution on physical robots
* 🧩 Modular & extensible architecture
* 👥 Designed for single-robot and multi-robot coordination

---

## System Pipeline

```
Audio File / Live Music
        ↓
Audio Feature Extraction
(Tempo, Beat, Loudness)
        ↓
Motion Mapping Engine
(Motion primitives + intensity scaling)
        ↓
ROS 2 Command Publisher
        ↓
JetRover Robot Execution
```

---

## Architecture Overview

### Core Components

* **Audio Processing Module**

  * Beat detection
  * Tempo estimation
  * Loudness analysis
* **Motion Mapping Engine**

  * Maps beats to motion primitives
  * Scales motion intensity using audio energy
* **ROS 2 Control Layer**

  * Publishes velocity and joint commands
  * Interfaces with robot base and arm
* **Robot Execution Layer**

  * JetRover wheels (normal / mecanum / tank)
  * Robotic arm gestures

---

## Motion Primitives

The choreography is built from reusable motion blocks:

* Base movements:

  * Forward / backward motion
  * Spin / rotation
  * Side movement (mecanum wheels)
* Arm gestures:

  * Wave
  * Nod
  * Lift / drop
* Beat-based triggers:

  * Strong beats → large motions
  * Soft beats → subtle motions

Motion timing and intensity are dynamically adjusted based on audio features.

---

## Technologies Used

* **Python**
* **ROS 2 (Humble)**
* **librosa** (audio analysis)
* **NumPy / SciPy**
* **Hiwonder JetRover SDK**
* **Linux (Ubuntu)**

---

## Hardware Setup

* Hiwonder JetRover robot

  * Normal wheels / mecanum wheels / tank tracks
* Robot arm
* On-board camera (optional)
* Laptop connected to robot via same Wi-Fi network
* Remote access via **NoMachine / SSH**

---

## Setup Instructions

### 1. Environment

```bash
sudo apt update
sudo apt install ros-humble-desktop
pip install librosa numpy scipy
```

### 2. Workspace

```bash
mkdir -p ~/ros2_ws/src
cd ~/ros2_ws
colcon build
source install/setup.bash
```

---

## Running the System

### Start ROS 2 nodes

```bash
ros2 run robot_controller motion_node
```

### Run music-to-motion pipeline

```bash
python3 music_to_motion.py --audio sample_music.wav
```

The robot will begin executing dance movements synchronized to the music.

---

## Multi-Robot Choreography

This framework supports:

* Shared beat timing across robots
* Coordinated choreography patterns
* Leader-follower dance behavior

The system was tested with **multiple JetRover robots performing synchronized routines**.

---

## Project Status

✅ Core pipeline complete
✅ Real-time robot dance execution
✅ Multi-robot demonstrations

---

## Future Extensions

* 🎭 Emotion-aware choreography (happy / sad / energetic)
* 📝 Lyric-based motion generation
* 🧠 Reinforcement Learning for adaptive dance styles
* 🌐 Simulation support (Gazebo)
* 🎶 Live microphone input

---
## License

**Academic & Educational Use — Macquarie University**

---
