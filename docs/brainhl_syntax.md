# BrainHL Language Syntax (v0.1)

BrainHL is a Domain-Specific Language (DSL) designed to be simple, readable, and declarative. Its purpose is to define the architecture of a neural network, not to program its logic. The logic is handled by the C++ engine and orchestrated by Python.

The language is based on commands followed by parameters. Comments can be added using `//`.

---

## 1. `region` Command

Defines a spatial region in the 3D simulation space. This is useful for organizing neuron populations visually and conceptually.

**Syntax:**
`region <name> [<x1>, <y1>, <z1>] to [<x2>, <y2>, <z2>]`

- `<name>`: A unique identifier for the region.
- `[<x1>, <y1>, <z1>]`: The starting coordinates of the region's bounding box.
- `[<x2>, <y2>, <z2>]`: The ending coordinates of the region's bounding box.

**Example:**
```brainhl
// Defines a 2D area for lexical input neurons
region entrada_lexica [0, 0, 0] to [10, 10, 0]

// Defines a separate area for output neurons
region salida [20, 0, 0] to [30, 10, 0]
```

---

## 2. `create` Command

Populates a previously defined region with a number of neurons of a specific type.

**Syntax:**
`create <count> neurons of type <neuron_type> in <region_name>`

- `<count>`: The number of neurons to create.
- `<neuron_type>`: A string identifier for the type of neuron (e.g., `Palabra`, `Sensor`, `Concepto`). The behavior associated with each type is defined in the C++ engine.
- `<region_name>`: The name of the region where these neurons will be placed.

**Example:**
```brainhl
// Creates 100 neurons of type 'Palabra' in the 'entrada_lexica' region.
create 100 neurons of type Palabra in entrada_lexica

// Creates 8 output neurons.
create 8 neurons of type Salida in salida
```

---

## 3. `connect` Command

Defines the synaptic connections between populations of neurons.

**Syntax:**
`connect all <source_type> to all <dest_type> with weight range [<min_w>, <max_w>] [with plasticity rate <rate>]`

- `<source_type>`: The type of the presynaptic neurons.
- `<dest_type>`: The type of the postsynaptic neurons.
- `[<min_w>, <max_w>]`: The range for the initial random weight of the connections.
- `[with plasticity rate <rate>]` (Optional): If this clause is present, the connections are created as "plastic" and will be subject to learning rules (like STDP). `<rate>` is the learning rate.

**Example:**
```brainhl
// Create plastic connections from input to output
connect all Palabra to all Salida with weight range [0.0, 0.1] with plasticity rate 0.01

// Create fixed, recurrent connections within the output layer
connect all Salida to all Salida with weight range [-0.1, 0.0]
```
