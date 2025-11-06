# ⚛️ Quantum Random Number Generator (QRNG)

Generate truly random numbers using real IBM quantum computers! This project leverages quantum superposition and measurement to create random numbers that are fundamentally unpredictable, unlike classical pseudo-random number generators.

## 🌟 What Makes This Special?

Traditional random number generators are **pseudo-random** - they use mathematical algorithms that are ultimately deterministic. This quantum random number generator uses **true quantum randomness** from the superposition and measurement of qubits on real quantum hardware.

When a qubit in superposition is measured, quantum mechanics guarantees the outcome is fundamentally random - not just computationally difficult to predict, but truly unpredictable.

## 🎯 Features

- ✅ Uses **real IBM quantum hardware** (not simulators)
- ✅ Built with **Qiskit SDK 2.x** and **Qiskit Runtime API** (2025)
- ✅ Compatible with **IBM Quantum Open Plan** (free tier)
- ✅ Automatic backend selection (least busy quantum computer)
- ✅ Circuit optimization and transpilation
- ✅ Comprehensive result visualization
- ✅ Statistical analysis of generated numbers

## 📋 Prerequisites

### IBM Quantum Account
1. Create a free account at [IBM Quantum Platform](https://quantum.ibm.com/)
2. Navigate to your account settings
3. Copy your API token

### Python Requirements
- Python 3.8 or higher
- Qiskit SDK 2.x
- Qiskit IBM Runtime
- Matplotlib

## 🚀 Installation

### 1. Clone or Download
```bash
# Save the qrng.py file to your local machine
```

### 2. Install Dependencies
```bash
pip install qiskit qiskit-ibm-runtime matplotlib
```

### 3. Configure Your API Token
Open `qrng.py` and replace the placeholder with your actual API token:
```python
API_TOKEN = "your_actual_api_token_here"
```

## 💻 Usage

### Basic Usage
Simply run the script:
```bash
python qrng.py
```

### Customization
Modify the configuration variables in the `main()` function:

```python
NUM_QUBITS = 6    # Number range: 0 to 2^NUM_QUBITS - 1
NUM_SHOTS = 1024  # Number of random numbers to generate
```

**Examples:**
- `NUM_QUBITS = 5` → generates numbers from 0 to 31
- `NUM_QUBITS = 8` → generates numbers from 0 to 255
- `NUM_QUBITS = 10` → generates numbers from 0 to 1023

## 🔬 How It Works

### The Quantum Process

1. **Initialization**: Qubits start in the |0⟩ state
2. **Superposition**: Hadamard gates create equal superposition (|0⟩ + |1⟩)/√2
3. **Measurement**: Quantum measurement randomly collapses each qubit to 0 or 1
4. **Conversion**: Binary strings are converted to decimal random numbers

### Circuit Example (3 qubits)
```
     ┌───┐┌─┐
q_0: ┤ H ├┤M├
     ├───┤└╥┘
q_1: ┤ H ├─╫─
     ├───┤ ║ 
q_2: ┤ H ├─╫─
     └───┘ ║ 
```

Each `H` (Hadamard) gate creates quantum randomness through superposition.

## 📊 Output

The program generates:

1. **Console Output**: 
   - Connection status and backend information
   - Sample random numbers
   - Statistical analysis (min, max, mean)
   - Distribution of measurement outcomes

2. **Histogram**: Saved as `qrng_results.png`
   - Visual representation of the random number distribution
   - Shows how uniformly distributed the results are

### Example Output
```
🎯 QUANTUM RANDOM NUMBER GENERATOR - RESULTS
======================================================================
Backend Used: ibm_brisbane
Total Measurements: 1024
Number Range: 0 to 63
Unique Values Generated: 58

📊 Sample Random Numbers (first 20):
[42, 7, 19, 55, 31, 8, 44, 23, 60, 15, 3, 37, 51, 12, 29, 46, 6, 58, 21, 34]

📈 Statistics:
   Min: 0
   Max: 63
   Mean: 31.47
```

## ⚠️ Important Notes

### IBM Quantum Open Plan Limits
- **10 minutes** of quantum time per 28-day rolling window
- This script typically uses **30-60 seconds** per run
- Monitor your usage at [IBM Quantum Platform](https://quantum.ibm.com/)

### Queue Times
- Your job enters a queue with other users
- Wait times vary from seconds to minutes depending on backend load
- The script automatically selects the least busy quantum computer

### True Randomness
The randomness comes from quantum measurement and is certified by the laws of quantum mechanics. This is fundamentally different from classical random number generators, which are deterministic algorithms.

## 🛠️ Troubleshooting

### Authentication Errors
- Double-check your API token is correct
- Ensure you're copying the entire token with no extra spaces

### No Available Backends
- All quantum systems may be down for maintenance
- Check [IBM Quantum Platform status](https://quantum.ibm.com/)
- Try again later

### Quota Exceeded
- You've used your 10 minutes of quantum time
- Wait for your 28-day window to reset
- Check remaining time at IBM Quantum Platform

### Import Errors
```bash
# Ensure you have the latest versions
pip install --upgrade qiskit qiskit-ibm-runtime
```

## 📚 Learn More

### Quantum Computing Concepts
- [IBM Quantum Learning](https://learning.quantum.ibm.com/)
- [Qiskit Textbook](https://qiskit.org/learn/)

### Qiskit Documentation
- [Qiskit Runtime Documentation](https://docs.quantum.ibm.com/api/qiskit-ibm-runtime)
- [Qiskit SDK Documentation](https://docs.quantum.ibm.com/api/qiskit)

### Research Papers
- Quantum random number generation is used in cryptography, simulations, and secure communications
- Search for "quantum random number generator" on [arXiv.org](https://arxiv.org/)

## 📄 License

This code is provided for educational purposes. Feel free to modify and use it for your own quantum experiments!

## 🤝 Contributing

Ideas for improvements:
- Add support for saving random numbers to file
- Implement statistical randomness tests (NIST test suite)
- Create a web interface for the generator
- Add real-time visualization during execution
- Compare quantum vs. classical random distributions

## 🎓 Educational Use

This project is perfect for:
- Learning quantum computing fundamentals
- Understanding quantum superposition and measurement
- Exploring Qiskit and IBM Quantum Platform
- Demonstrating true vs. pseudo randomness
- Teaching quantum mechanics principles

---

**Made with ⚛️ using IBM Quantum Platform**

*Questions? Check the [IBM Quantum Platform documentation](https://docs.quantum.ibm.com/) or visit the [Qiskit community](https://qiskit.slack.com/).*
