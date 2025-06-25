# BrainHL - High-Performance SNN Simulator

[![Version][version-shield]][version-url]
[![License][license-shield]][license-url]

**BrainHL** is a high-performance engine for simulating Spiking Neural Networks (SNNs), developed by NetechAI. It combines a powerful C++ core with a user-friendly Python API, allowing for both efficient, large-scale simulations and dynamic, script-based network management.

## Key Features

- **High-Performance Core:** The simulation engine is written in modern C++ for maximum speed and efficiency.
- **Declarative Language:** Define complex network architectures easily using the simple and intuitive `.brainhl` file format.
- **Command-Line Interpreter:** Use the standalone `bhl.exe` tool to quickly load and simulate network files.
- **Python API:** Seamlessly integrate BrainHL into your Python workflows. Create, modify, and simulate networks on the fly.
- **Easy Installation:** A simple Windows installer gets you up and running in minutes.

---

## 1. Installation

The easiest way to install BrainHL is by using the official installer.

1.  Go to the [**Releases**](https://github.com/NetechAI/BrainHL) page of this repository.
2.  Download the latest installer, `BrainHL-0.1-Beta-setup.exe`.
3.  Run the installer. We recommend checking the option **"Add application directory to your system PATH"** to make `bhl.exe` available from any terminal.

## 2. Quick Start

BrainHL can be used in two primary ways: via the command-line interpreter or as a Python module.

### Using the Command-Line (`bhl.exe`)

This is the simplest way to run a simulation from a file.

```bash
# Load and parse a network file
bhl.exe path/to/your/network.brainhl

# Show help message
bhl.exe --help

# Check version information
bhl.exe --version
```

### Using the Python API

The Python API provides full control over the network for dynamic scripting and integration.

```python
import brainhl

# Create a network instance
network = brainhl.DynamicNetwork()

# Create a parser instance
parser = brainhl.BrainHLParser()

# Load a network from a file
filepath = "path/to/your/network.brainhl"
if parser.parse(filepath, network):
    print(f"Network loaded successfully!")
    print(f"  - Neurons: {network.getNeuronCount()}")
    print(f"  - Connections: {len(network.getAllConnections())}")
else:
    print("Failed to load network.")

# You can now interact with the network object
# (e.g., add neurons, connections, run simulation steps, etc.)
```

## 3. The BrainHL Language

BrainHL uses a simple, human-readable language to define network regions, neurons, and connections. For a complete guide on syntax and commands, please see our detailed documentation:

- **[BrainHL Language Syntax Guide](docs/brainhl_syntax.md)**

## 4. License

This project is licensed under the Apache 2.0 License. See the [LICENSE](LICENSE) file for details.

---

*Copyright (c) 2025 NetechAI*

[version-shield]: https://img.shields.io/badge/version-0.1%20Beta-blue.svg
[version-url]: https://github.com/NetechAI/BrainHL

[license-shield]: https://img.shields.io/badge/License-Apache%202.0-green.svg
[license-url]: LICENSE