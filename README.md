# 🚀 BrainHL – High-Performance Spiking Neural Network (SNN) Simulator

[![Version][version-shield]][version-url]
[![License][license-shield]][license-url]

**BrainHL** is a blazing-fast simulation engine for **Spiking Neural Networks (SNNs)**, designed by **NetechAI**. Built on a modern C++ core and paired with a clean Python API, BrainHL empowers developers, researchers, and AI hobbyists to build, simulate, and experiment with brain-like architectures using simple, declarative `.brainhl` files.



## ✨ Key Features

* ⚡ **High-Performance C++ Core**
  Written in optimized C++ for large-scale, real-time neural simulation.

* 🧠 **Declarative Network Language**
  Design complete SNNs using minimal code with the `.brainhl` format.

* 🛠️ **Command-Line Interface (`bhl.exe`)**
  Run simulations instantly without writing a single line of Python.

* 🐍 **Python API Integration**
  Seamlessly embed BrainHL into your Python pipelines for full control.

* 📦 **Easy Setup (Windows Installer)**
  Quick installer with optional PATH integration—ready in minutes.

* 🧪 **Supports Learning**
  Includes Hebbian and supervised learning mechanisms for dynamic networks.


## 🔧 Installation

To get started:

1. Head to the [**Releases**](https://github.com/NetechAI/BrainHL/releases) page.
2. Download `BrainHL-0.1-Beta-setup.exe`.
3. Run the installer. Check **"Add to PATH"** to access `bhl.exe` globally from your terminal.



## ⚡ Quick Start

### ➤ Run a Simulation via CLI

```bash
# Run a BrainHL file
bhl.exe path/to/network.brainhl

# View help
bhl.exe --help

# Display version
bhl.exe --version
```

---

### ➤ Python Integration Example

```python
import brainhl

# Initialize the network and parser
network = brainhl.DynamicNetwork()
parser = brainhl.BrainHLParser()

# Load a network definition
if parser.parse("path/to/network.brainhl", network):
    print("✅ Network loaded!")
    print(f"Neurons: {network.getNeuronCount()}")
    print(f"Connections: {len(network.getAllConnections())}")
else:
    print("❌ Failed to load network.")
```

You can now manipulate the network: stimulate neurons, add/remove connections, simulate behavior, and more.



## 📘 BrainHL Language

BrainHL uses a concise, readable syntax to define neurons, regions, synaptic connections, thresholds, and learning behavior.

* 📄 [BrainHL Language Reference](docs/brainhl_syntax.md)


## 📄 License

BrainHL is released under the **Apache 2.0 License**.
See the full [LICENSE](LICENSE) for usage and redistribution terms.



> © 2025 **NetechAI** – Build brains, not boilerplate.

[version-shield]: https://img.shields.io/badge/version-0.1%20Beta-blue.svg
[version-url]: https://github.com/NetechAI/BrainHL
[license-shield]: https://img.shields.io/badge/License-Apache%202.0-green.svg
[license-url]: LICENSE

