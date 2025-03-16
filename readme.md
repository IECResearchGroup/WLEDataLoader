# WLEdataloader Framework

WLEdataloader is a flexible and efficient data loading framework designed to handle various datasets for wireless communication research. This framework provides tools to preprocess, load, and analyze data, making it easier for researchers to work with large datasets.

## WLE Dataset
| **Trace-set** | **Paper Title** | **Download Link**  |
|-|-|-|
| **Rutgers** | Creating wireless multi-hop topologies on space-constrained indoor testbeds through noise injection | [Download](http://clouds.iec-uit.com/wireless-link-estimation/Rutgers.zip) |
| **Colorado** | The impact of directional antenna models on simulation accuracy| [Download](http://clouds.iec-uit.com/wireless-link-estimation/Colorado.zip) |
| **JSI** | Optimization of ultra-narrowband wireless communication: an experimental case study | [Download](http://clouds.iec-uit.com/wireless-link-estimation/JSI_SIGFOX.zip) |
| **Packet-meta** | Experimental study for multi-layer parameter configuration of WSN links| [Download](http://clouds.iec-uit.com/wireless-link-estimation/Packetmetadata.zip) |
|**IEC_WLE24** | Our dataset | [Infomation](./IEC_WLE24.md) or [Download](http://clouds.iec-uit.com/wireless-link-estimation/RASP_COL.zip)

## Features

- Support for multiple datasets (e.g., Rutgers, Colorado)
- Data preprocessing and feature engineering
- Easy-to-use API for data loading and splitting
- Customizable data transformations
- Integration with popular machine learning libraries

## Installation

You can install the WLEdataloader framework using pip:

```bash
pip install wledataloader
```

## Usage

### 1. Import the library

```python
from wledataloader import ColoradoLoader
from wledataloader import JsiSigfoxLoader
from wledataloader import PktMetaLoader
from wledataloader import RutgersLoader
from wledataloader import IECWLE24Loader
```

- ColoradoLoader: Load data from Colorado dataset
- JsiSigfoxLoader: Load data from JSI Sigfox dataset
- PktMetaLoader: Load data from PktMeta dataset
- RutgersLoader: Load data from Rutgers dataset
- IECWLE24Loader: Load data from IECWLE24 dataset

### 2. Initialize the `ColoradoLoader` object

```python
data = ColoradoLoader(seed=0xDEADBEEF, printable=True, rate_list=[0.9, 0.1, 0.0], save_csv=True, rssi_process_type=1)
```

This initializes an instance of `ColoradoLoader`, automatically checking and managing cached data.

### 3. Prepare the dataset

```python
data.PrepareData(reload=False, extend_feature=True)
```

#### Parameters:

- `reload` (bool, default `False`): If `True`, reloads data from the source, ignoring cached files.
- `extend_feature` (bool, default `True`): If `True`, generates additional features for analysis or model training.

### 4. Check dataset shape

```python
print(data._data_df.shape)
```

### 5. Analyze and Prepare Data for Training

#### a. Perform Basic Analysis

The `ShowBasicAnalysis()` method provides a quick overview of the dataset, including statistical summaries and visualizations.

```python
data.ShowBasicAnalysis()
```

#### b. Extract Features and Labels

```python
X, y = data.GetXY()
```

#### c. Split Data into Training and Testing Sets

```python
X_train, X_test, y_train, y_test = data.TrainTestSplit(test_size=0.2)
```

##### Parameters:
- `test_size` (float, default `0.2`): The proportion of the dataset to include in the test split.

### Example Workflow

```python
from wledataloader import ColoradoLoader

# Initialize loader
data = ColoradoLoader()

# Prepare dataset
data.PrepareData(reload=False, extend_feature=True)

# Perform basic analysis
data.ShowBasicAnalysis()

# Extract features and labels
X, y = data.GetXY()

# Split data into training and testing sets
X_train, X_test, y_train, y_test = data.TrainTestSplit(test_size=0.2)

# Display dataset shapes
print("Training set shape:", X_train.shape, y_train.shape)
print("Testing set shape:", X_test.shape, y_test.shape)
```

## Notes

- The library may require an internet connection if the data is not cached locally.
- If missing data errors occur, try setting `reload=True` in `PrepareData()`.

## Contributing
We welcome contributions to the WLEdataloader framework. If you have any suggestions, bug reports, or feature requests, please open an issue on the GitHub repository.

## License
This project is licensed under the MIT License. See the LICENSE file for more details.

## Contact
For any questions or inquiries, please contact the project maintainers at [email@example.com].

