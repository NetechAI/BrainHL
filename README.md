# BrainHL

### Simulate complex neural networks with less than 10 lines of code.

[![License: Apache 2.0](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](LICENSE)

**BrainHL is a high-performance engine for simulating Spiking Neural Networks (SNNs), designed for speed, flexibility, and ease of use. It combines a powerful C++ backend with a simple, declarative language to bridge the gap between neuroscience concepts and computational modeling.**

## Core Philosophy

BrainHL is built on the principle of **Separation of Concerns**. The project is composed of two main parts:

1.  **The C++ Engine:** A highly-optimized, standalone library that handles the heavy lifting of creating, connecting, and simulating large-scale neural networks. It is completely independent of any other language.
2.  **The Consumers:** Interfaces that use the C++ engine. This includes:
    *   A **command-line interpreter** (`brainhl.exe`) for running simulations directly.
    *   **Python bindings** (`.pyd`) to allow for rapid prototyping, training, and integration with the rich ecosystem of data science libraries.

This architecture means you can design a network once and simulate it anywhere, from a high-performance computing cluster to an embedded system in a robot.

## Key Features

*   **High-Performance C++ Core:** The simulation backend is written in modern C++ for maximum performance and efficiency.
*   **Declarative Syntax (`.brainhl`):** Define entire network architectures using a simple, human-readable language. Describe regions, neuron populations, and connection strategies, and let the engine handle the implementation.
*   **Dynamic Topologies:** The `DynamicNetwork` class allows for networks that can change and grow during the simulation.
*   **Standalone Interpreter:** Run simulations natively with the compiled `brainhl.exe`, no other dependencies required.
*   **Python Integration:** Optional Python bindings provide a high-level interface to control the simulation, feed it data, and analyze the results.

## Getting Started

To get started, you will need a C++ compiler (with C++17 support) and CMake. 

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/your-username/BrainHL.git
    cd BrainHL
    ```

2.  **Configure and build the project:**
    ```bash
    mkdir build
    cd build
    cmake ..
    cmake --build .
    ```

3.  **Run a simulation:**
    After building, you can find the interpreter in the `Release` or `Debug` folder.
    ```bash
    ./Release/brainhl.exe ../examples/your_example.brainhl
    ```

BrainHL is a sandbox for innovation. While the included example is a simple language classifier, the platform is designed for much more:

- **Custom Neural Classifiers:** Solve unique classification problems with bespoke architectures.
- **Associative Memory Models:** Simulate systems that can store and retrieve information based on partial cues.
- **Spiking Neural Network (SNN) Research:** Extend the C++ core to model more biologically realistic, event-driven neurons.
- **Studies in Synaptic Plasticity:** Experiment with different learning rules by modifying how weights are adjusted in the Python training script.

## Getting Started

Follow these steps to build and run the project on your local machine.

### Prerequisites

- A modern C++ compiler (GCC, Clang, MSVC)
- [CMake](https://cmake.org/download/) (version 3.10+)
- [Python](https://www.python.org/downloads/) (version 3.6+)

### Installation

1.  **Clone the repository (replace `YOUR_USERNAME`):**
    ```bash
    git clone https://github.com/YOUR_USERNAME/BrainHL.git
    cd BrainHL
    ```

2.  **Install Python dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

3.  **Build the C++ backend:**
    ```bash
    mkdir build
    cd build
    cmake ..
    cmake --build . --config Release
    ```
    This will compile the backend and create the Python module (`brainhl_core.pyd` or similar) in the project's root directory.

## Example: Language Classifier

The project includes an example to classify words into semantic categories.

1.  **Train the model:**
    ```bash
    python examples/python/train_classifier.py
    ```
    This script will read data from [`training_data.txt`](examples/python/training_data.txt), train the network, and save the learned weights to the `trained_models/` directory.

2.  **Test the classifier:**
    ```bash
    python examples/python/test_classifier.py
    ```
    You can now enter words (e.g., `perro`, `libro`, `fuego`) and see how the network classifies them.

## License

This project is licensed under the Apache 2.0 License. See the [`LICENSE`](LICENSE) file for details.

## Contributing

Contributions are welcome! If you have ideas for new features, improvements, or have found a bug, please open an issue or submit a pull request.

---

*Project developed by Joaquín Stürtz (NetechAI) with the assistance of Cascade.*