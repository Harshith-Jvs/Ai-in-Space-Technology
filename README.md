# 🪐 Cave Explorer — AI-Powered Mars Cave Exploration

Cave Explorer is a Python-based robotics simulation in which an autonomous quadruped robot explores randomly generated Martian lava tubes. The robot maps unknown underground environments, avoids obstacles, identifies potential scientific targets, manages its battery, and attempts to return safely to the surface.

The project demonstrates how AI search algorithms, autonomous navigation, and robotic mapping can support future Mars cave exploration missions.

## ✨ Features

- **Procedural Cave Generation:** Generates winding tunnels, branching passages, chambers, dead ends, and obstacles using reproducible random seeds.
- **Autonomous Exploration:** Uses frontier-based exploration to identify promising unexplored regions.
- **Dynamic Algorithm Switching:** Selects navigation and path-planning algorithms based on the current environment and mission conditions.
- **Path Planning:** Implements algorithms such as A*, Dijkstra, and Theta*.
- **Obstacle Avoidance:** Uses simulated LiDAR sensing, collision detection, and recovery behaviors to navigate around obstacles.
- **Occupancy Grid Mapping:** Builds a map from the robot's sensor observations instead of relying on the complete cave layout.
- **Scientific Exploration:** Simulates mineral detection and the investigation of potential microbial life.
- **Battery Management:** Monitors energy consumption and triggers return-to-base behavior when necessary.
- **Map Export:** Saves the discovered map, robot path, mission metadata, and exploration logs for later analysis.
- **Reproducible Missions:** Uses configurable random seeds to generate the same cave for repeatable experiments.

## 🧠 AI Techniques

| Technique | Purpose |
|---|---|
| Frontier-based exploration | Selects unexplored regions |
| Utility-based exploration | Prioritizes promising exploration targets |
| A* search | Finds cost-aware paths |
| Dijkstra's algorithm | Provides a shortest-path baseline |
| Theta* search | Supports more direct paths through open areas |
| Potential-field control | Helps avoid nearby obstacles |
| Recovery behaviors | Respond to collisions and lack of movement |
| State-machine controller | Switches algorithms and manages mission phases |

The controller adapts its navigation strategy as the robot discovers obstacles, enters different cave regions, or approaches its battery safety limit.

## 🛠️ Tech Stack

- Python 3.11+
- Pygame-CE
- NumPy
- Procedural environment generation
- Grid-based robotic mapping and path planning

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone <your-repository-url>
cd cave-explorer
```

### 2. Install dependencies

```bash
python -m venv .venv
```

Activate the environment:

**Windows**
```powershell
.venv\Scripts\Activate.ps1
```

**macOS / Linux**
```bash
source .venv/bin/activate
```

Install the required packages:

```bash
python -m pip install -r requirements.txt
```

### 3. Run the simulation

```bash
python main.py --seed 27125 --difficulty Small
```

Change the seed to generate another cave. Reuse the same seed to reproduce an environment.

## 🎮 Controls

| Key | Action |
|---|---|
| `Space` | Pause or resume |
| `+` / `-` | Increase or decrease simulation speed |
| `R` | Generate a new cave |
| `S` | Restart the same cave |
| `A` | Enable automatic algorithm selection |
| `1`–`7` | Manually select a supported algorithm |
| `T` | Toggle ground-truth map |
| `F` | Toggle fog of war |
| `L` | Toggle lighting |
| `M` | Toggle minimap |
| `G` | Toggle debugging overlays |
| `E` | Export mission data |
| `F11` | Toggle fullscreen |
| `Esc` | Return to the menu or quit |

## 🗺️ Mapping and Data Export

The robot constructs its own map using simulated sensor observations. Unknown areas remain unexplored until detected by its sensors.

The project distinguishes between:

- **Ground-truth map:** The complete generated cave, used to evaluate exploration performance.
- **Robot belief map:** The map built from the robot's own observations and used for navigation.

Mission data can be exported to the `reports/` directory. Depending on the export implementation, files include a map image, occupancy-map data, robot path history, mission metadata, and algorithm-switch logs.

The exported data can represent a cave survey that a real rover might transmit to Earth after establishing communication with a surface relay.

## 🎯 Project Objective

The goal is to demonstrate how autonomous robots can explore hazardous underground environments where direct human control is difficult. By combining mapping, search algorithms, obstacle avoidance, and energy-aware planning, Cave Explorer provides an educational foundation for studying AI in planetary exploration.

## ⚠️ Limitations

- This is an educational simulation, not a flight-ready robotics system.
- The environment and sensors are simulated rather than based on validated Mars hardware.
- Navigation and mapping use a 2D grid rather than a complete 3D terrain model.
- Scientific detections are illustrative and do not establish the existence of life.
- Mission completion and full cave coverage are not guaranteed for every random environment.

## 🔮 Future Improvements

- 3D terrain mapping and more realistic cave rendering.
- Cooperative exploration using multiple robots.
- Improved localization and loop closure.
- More robust recovery and energy-aware route planning.
- More realistic sensor models and scientific measurements.

## 📄 License

Choose an open-source license for your repository, such as the MIT License, and include its license text in a `LICENSE` file.

---

**Cave Explorer** — Exploring the unknown, one passage at a time.
