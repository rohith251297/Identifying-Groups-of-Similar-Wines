```markdown
# Identifying-Groups-of-Similar-Wines

## Overview
This project implements a `matrix` class that allows for loading data from a CSV file, standardizing the data, and performing clustering operations. The clustering algorithms include basic distance calculations and methods for updating cluster weights based on separation within and between clusters. This implementation is suitable for exploring clustering techniques and understanding how different metrics can affect clustering results.

## Features
- Load matrix data from a CSV file.
- Standardize the matrix data.
- Compute Euclidean distance and weighted Euclidean distance between rows.
- Calculate frequency of elements in the matrix.
- Assign groups based on nearest centroids.
- Compute centroids for clusters.
- Calculate separation within and between clusters.
- Update weights based on separation metrics.

## Requirements
- Python 3.11
- NumPy

You can install NumPy using pip:
```bash
pip install numpy
```

## Usage
### Matrix Class
The `matrix` class is defined with the following methods:
- `__init__(self, file_path=None)`: Initializes the matrix object and loads data from a CSV file if a file path is provided.
- `load_from_csv(self, file_path)`: Loads data from a specified CSV file into the matrix.
- `standardise(self)`: Standardizes the matrix data by centering and scaling.
- `get_distance(self, other_matrix, row_i)`: Computes the Euclidean distance from a specified row to all rows in another matrix.
- `get_weighted_distance(self, other_matrix, weights, row_i)`: Computes the weighted Euclidean distance from a specified row to all rows in another matrix using a weight vector.
- `get_count_frequency(self)`: Returns the frequency of each unique element in the matrix.

### Clustering Functions
The project includes several functions for clustering operations:
- `get_initial_weights(m)`: Generates initial random weights that sum to 1.
- `get_centroids(data, S, K)`: Computes centroids for the clusters.
- `get_separation_within(data, centroids, S, K)`: Calculates separation within clusters.
- `get_separation_between(data, centroids, S, K)`: Calculates separation between clusters.
- `get_groups(data, K)`: Assigns groups based on the nearest centroids.
- `get_new_weights(data, centroids, weights, S, K)`: Updates the weights vector.

### Running Tests
To run tests, provide a CSV file path and call the `run_test(file_path)` function:
```python
file_path = r"C:\\path\\to\\your\\data.csv"
run_test(file_path)
```

### Example Usage
```python
# Create a matrix object
m = matrix(file_path)

# Standardize the data
m.standardise()

# Compute distances
other_matrix = matrix()
other_matrix.array_2d = m.array_2d[:3]  # Subset for testing
row_index = 10
distance = m.get_distance(other_matrix, row_index)

# Get frequencies
frequency = m.get_count_frequency()

# Perform clustering
K = 2
S = get_groups(m, K)
centroids = get_centroids(m, S, K)
```

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments
- Thanks to the NumPy community for their support and documentation.
```
