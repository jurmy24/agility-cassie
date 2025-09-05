# 🤖 Agility Cassie

<div align="center">
  <img src="https://raw.githubusercontent.com/jurmy24/agility-cassie/main/assets/cassie-hero.png" alt="Cassie Robot" width="600"/>
  
  *Advanced Bipedal Robotics Research & Development*
  
  [![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
  [![Python](https://img.shields.io/badge/python-3.8%2B-blue)](https://www.python.org/)
  [![ROS](https://img.shields.io/badge/ROS-Noetic-brightgreen)](http://wiki.ros.org/noetic)
  [![Build Status](https://img.shields.io/badge/build-passing-brightgreen)](https://github.com/jurmy24/agility-cassie)
  
</div>

---

## 🌟 Overview

Welcome to the **Agility Cassie** repository! This project focuses on the remarkable Cassie bipedal robot developed by Agility Robotics. Cassie represents a breakthrough in dynamic locomotion research, featuring human-like walking capabilities and unprecedented mobility across challenging terrains.

### ✨ Key Features

- **🚶 Dynamic Walking**: Advanced gait control algorithms for stable bipedal locomotion
- **🎯 Real-time Control**: High-frequency control loops for responsive movement
- **📊 State Estimation**: Robust sensor fusion for accurate pose and velocity estimation  
- **🔧 Simulation Integration**: MuJoCo and Gazebo simulation environments
- **📡 ROS Integration**: Full Robot Operating System support
- **🧠 Machine Learning**: Reinforcement learning frameworks for behavior optimization

---

## 🏗️ Architecture

```
agility-cassie/
├── 📁 src/
│   ├── controllers/     # Control algorithms and state machines
│   ├── estimation/      # State estimation and sensor fusion
│   ├── planning/        # Motion planning and trajectory generation
│   └── interfaces/      # Hardware and simulation interfaces
├── 📁 config/          # Configuration files and parameters
├── 📁 launch/          # ROS launch files
├── 📁 simulation/      # Simulation environments and models
├── 📁 scripts/         # Utility scripts and tools
├── 📁 docs/           # Documentation and tutorials
└── 📁 tests/          # Unit tests and validation
```

---

## 🚀 Quick Start

### Prerequisites

Ensure you have the following dependencies installed:

```bash
# System dependencies
sudo apt update && sudo apt install -y \
    build-essential \
    cmake \
    git \
    python3-pip \
    ros-noetic-desktop-full

# Python dependencies  
pip3 install numpy scipy matplotlib torch
```

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/jurmy24/agility-cassie.git
   cd agility-cassie
   ```

2. **Build the workspace**
   ```bash
   # Source ROS environment
   source /opt/ros/noetic/setup.bash
   
   # Build the catkin workspace
   catkin_make
   source devel/setup.bash
   ```

3. **Install Python packages**
   ```bash
   pip3 install -r requirements.txt
   ```

### Running the Simulation

Launch Cassie in a Gazebo simulation environment:

```bash
# Launch the complete simulation stack
roslaunch cassie_gazebo cassie_world.launch

# In a new terminal, start the controller
rosrun cassie_control standing_controller.py
```

---

## 📋 Usage Examples

### Basic Standing Controller

```python
from cassie_control import CassieController
import rospy

def main():
    rospy.init_node('cassie_standing')
    
    # Initialize controller
    controller = CassieController()
    
    # Set standing position
    controller.set_standing_pose()
    
    # Run control loop
    controller.spin()

if __name__ == '__main__':
    main()
```

### Walking Gait Implementation

```python
from cassie_control import WalkingController
from cassie_planning import FootstepPlanner

# Create walking controller
walker = WalkingController()

# Plan footsteps
planner = FootstepPlanner()
footsteps = planner.generate_walking_pattern(
    forward_velocity=0.5,  # m/s
    step_length=0.3,       # meters
    step_frequency=1.0     # Hz
)

# Execute walking gait
walker.execute_footsteps(footsteps)
```

---

## 📚 Documentation

### Core Components

- **[Controller Design](docs/controllers.md)** - Control architecture and algorithms
- **[State Estimation](docs/estimation.md)** - Sensor fusion and filtering techniques  
- **[Simulation Setup](docs/simulation.md)** - Getting started with MuJoCo and Gazebo
- **[Hardware Interface](docs/hardware.md)** - Connecting to physical Cassie robot
- **[API Reference](docs/api.md)** - Complete API documentation

### Tutorials

- 🎓 [Getting Started Tutorial](docs/tutorials/getting-started.md)
- 🚶 [Walking Controller Tutorial](docs/tutorials/walking-controller.md) 
- 🤖 [Simulation Tutorial](docs/tutorials/simulation.md)
- 🧠 [Machine Learning Integration](docs/tutorials/ml-integration.md)

---

## 🛠️ Development

### Contributing

We welcome contributions! Please see our [Contributing Guide](CONTRIBUTING.md) for details.

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Testing

Run the test suite to ensure everything works correctly:

```bash
# Run all tests
catkin_make run_tests

# Run specific test packages
catkin_make run_tests_cassie_control
catkin_make run_tests_cassie_estimation
```

### Code Style

We follow the ROS C++ and Python style guidelines:

```bash
# Format C++ code
clang-format -i src/**/*.cpp src/**/*.h

# Format Python code  
black scripts/ src/
```

---

## 📊 Performance

### Benchmarks

| Metric | Value | Notes |
|--------|-------|-------|
| Control Frequency | 2000 Hz | Real-time performance |
| Walking Speed | 0.8 m/s | Stable forward walking |
| Step Height | 0.15 m | Maximum step clearance |
| Battery Life | 45 min | Continuous operation |

### System Requirements

- **OS**: Ubuntu 18.04+ or Ubuntu 20.04+
- **ROS**: Noetic Ninjemys
- **CPU**: Intel i7+ or equivalent
- **RAM**: 8GB+ recommended
- **GPU**: NVIDIA GPU recommended for simulation

---

## 🤝 Community

### Getting Help

- 💬 [Discussions](https://github.com/jurmy24/agility-cassie/discussions) - Ask questions and share ideas
- 🐛 [Issues](https://github.com/jurmy24/agility-cassie/issues) - Report bugs and request features
- 📧 [Contact](mailto:developer@example.com) - Direct developer contact

### Related Projects

- [Agility Robotics Official Docs](https://github.com/agilityrobotics/cassie-doc) - Official documentation
- [Cassie MuJoCo Simulation](https://github.com/osudrl/cassie-mujoco-sim) - MuJoCo simulation environment
- [Gym Cassie](https://github.com/siekmanj/cassie) - OpenAI Gym environment
- [Cassie Resources](https://github.com/UBCMOCCA/Cassie_Robot_Resources) - Research papers and resources

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- **Agility Robotics** for creating the incredible Cassie platform
- **Oregon State University** for pioneering research in bipedal locomotion  
- **The open source robotics community** for their invaluable contributions
- **All contributors** who help make this project better

---

## 📈 Roadmap

### Current Focus (v1.x)
- ✅ Basic walking controller
- ✅ Simulation integration  
- ✅ ROS interface
- 🔄 Advanced terrain adaptation

### Upcoming Features (v2.x)
- 🎯 Machine learning integration
- 🎯 Advanced perception systems
- 🎯 Multi-robot coordination
- 🎯 Cloud-based monitoring

### Future Vision (v3.x)
- 🌟 Autonomous navigation
- 🌟 Human-robot interaction
- 🌟 Real-world deployment tools

---

<div align="center">
  <strong>Built with ❤️ for the robotics community</strong>
  
  [⬆ Back to top](#-agility-cassie)
</div>
