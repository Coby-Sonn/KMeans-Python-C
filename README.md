# K-Means Clustering Implementation in Python and C

This repository contains an implementation of the K-Means clustering algorithm, leveraging both Python and C for optimized performance.

## Overview
- **Python Implementation**: Handles data processing and initialization using K-Means++.
- **C Extension**: Optimized clustering computation using linked lists for efficient memory management.

## Files
- `kmeans_pp.py` - Python implementation, including K-Means++ initialization.
- `kmeansmodule.c` - C extension implementing the core clustering logic.
- `setup.py` - Build script for compiling the C extension into a Python module.

## Installation
### Prerequisites
- Python 3.x installed.
- A C compiler such as `gcc`.

### Building the C Extension
Run the following command to compile the C module:
```sh
python setup.py build_ext --inplace
```
This will generate a shared library (`mykmeanssp.*.so` or `.pyd` on Windows) that can be imported into Python.

## How to Run
### Running the Python Implementation
#### Command Syntax:
```sh
python kmeans_pp.py <k> [<max_iter>] <epsilon> <input_file_1> <input_file_2>
```
- `<k>`: Number of clusters (integer > 1 and < N, where N is the number of points).
- `<max_iter>`: (Optional) Maximum number of iterations (default: 300, max: 1000).
- `<epsilon>`: Convergence threshold (float >= 0).
- `<input_file_1>`, `<input_file_2>`: CSV files containing the input data.

#### Example:
```sh
python kmeans_pp.py 3 300 0.001 data1.csv data2.csv
```

## Output Format
- The program prints the initial centroids' indices.
- The final cluster centroids are printed, with each centroid on a new line formatted to 4 decimal places.

## Notes
- Input files must be in CSV format with numerical values.
- The implementation uses the K-Means++ initialization method for better convergence.
- The Python script interfaces with the optimized C extension for better performance.

## License
This project is released under the MIT License.

