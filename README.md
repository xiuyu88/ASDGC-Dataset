# ASDGC-Dataset

This repository contains the benchmark datasets used in the experiments of **Adaptive-Scale Dynamic Graph Learning with Cross-Scale Global Fusion (ASDGC)** for non-stationary multivariate time series forecasting.

## Files in This Repository

```text
ASDGC-Dataset/
├── ETTm1.zip
├── ETTm2.zip
├── PEMS04.zip
├── PEMS07.zip.001
├── PEMS07.zip.002
├── exchange_rate.zip
├── illness.zip
├── solar-energy.zip
├── weather.zip
└── README.md
```

## Important Note for `PEMS07`

Because of repository file-size constraints, **PEMS07 is split into two archive parts**:

- `PEMS07.zip.001`
- `PEMS07.zip.002`

Please merge the two parts before extraction.

### Linux / macOS

```bash
cat PEMS07.zip.001 PEMS07.zip.002 > PEMS07.zip
unzip PEMS07.zip
```

### Windows (Command Prompt)

```bat
copy /b PEMS07.zip.001 + PEMS07.zip.002 PEMS07.zip
```

Then extract `PEMS07.zip` with your preferred decompression tool.

## Data Format

After extraction, each dataset is provided in **plain-text `.txt` format** for direct use in forecasting experiments.

### Format convention

- Each file is a **numeric matrix**.
- **Rows** correspond to time steps.
- **Columns** correspond to variables / sensors / series.
- The files are intended for direct loading in Python and other scientific-computing environments.

A typical loading method is:

```python
import numpy as np

x = np.loadtxt('your_dataset.txt', delimiter=',')
print(x.shape)   # [T, N]
```

If you prefer pandas:

```python
import pandas as pd

x = pd.read_csv('your_dataset.txt', header=None)
print(x.shape)
```

## Dataset Statistics

The following statistics are consistent with the benchmark setting reported in the ASDGC paper.

| Dataset       | Variables | Time Steps | Frequency | Domain      |
| ------------- | --------: | ---------: | --------- | ----------- |
| ETTm1         |         7 |     69,680 | 15 min    | Temperature |
| ETTm2         |         7 |     69,680 | 15 min    | Temperature |
| Exchange-Rate |         8 |      7,588 | Daily     | Economy     |
| Weather       |        21 |     52,696 | 10 min    | Weather     |
| Solar-Energy  |       137 |     52,560 | 10 min    | Energy      |
| ILI           |         7 |        966 | Weekly    | Illness     |
| PEMS04        |       307 |     16,992 | 5 min     | Traffic     |
| PEMS07        |       883 |     28,224 | 5 min     | Traffic     |

## Brief Description of Each Dataset

### ETTm1 / ETTm2

Electricity Transformer Temperature (ETT) datasets contain seven transformer-related variables recorded at a **15-minute** resolution. They are widely used to evaluate multivariate forecasting models under strong periodicity and long-term trend variation.

### Exchange-Rate

This dataset contains the **daily exchange rates of eight countries** and is a standard low-frequency benchmark for financial multivariate forecasting.

### Weather

This dataset includes **21 meteorological variables** recorded every **10 minutes**. It is commonly used to test forecasting models under complex environmental dynamics.

### Solar-Energy

This dataset records **solar power generation from 137 plants** at a **10-minute** interval. It is a representative benchmark for non-stationary renewable-energy forecasting due to abrupt fluctuations and ramp events.

### ILI

The ILI dataset contains **weekly influenza-like illness ratios** and is commonly used for long-horizon public-health forecasting.

### PEMS04 / PEMS07

PEMS04 and PEMS07 are large-scale traffic benchmarks derived from the **California Transportation Agencies (CalTrans) Performance Measurement System (PeMS)**. In common benchmark preprocessing, the traffic observations are aggregated to **5-minute** intervals, making them suitable for spatio-temporal multivariate forecasting research.

## Suggested Directory Layout After Extraction

A convenient local organization is:

```text
multivariate-time-series-data/
├── ETTm1/
│   └── ETTm1.txt
├── ETTm2/
│   └── ETTm2.txt
├── exchange_rate/
│   └── exchange_rate.txt
├── weather/
│   └── weather.txt
├── solar-energy/
│   └── solar-energy.txt
├── illness/
│   └── illness.txt
├── PEMS04/
│   └── PEMS04.txt
└── PEMS07/
    └── PEMS07.txt
```

If your local extracted file names differ slightly, please adapt the path in your code accordingly.

## References and Data Sources

The benchmark descriptions in this repository are aligned with the ASDGC paper and standard public benchmark sources. Helpful references include:

1. **TimeSeriesDatasets benchmark collection**  
   https://github.com/juyongjiang/TimeSeriesDatasets

2. **ETT dataset / Informer**  
   https://github.com/zhouhaoyi/ETDataset

3. **Common multivariate forecasting benchmark collection**  
   https://github.com/laiguokun/multivariate-time-series-data

4. **Weather dataset source**  
   https://www.bgc-jena.mpg.de/wetter/

5. **ILI source (CDC FluView)**  
   https://gis.cdc.gov/grasp/fluview/fluportaldashboard.html

6. **Traffic benchmark preprocessing reference (including PEMS family)**  
   https://github.com/guoshnBJTU/ASTGNN/tree/main/data

## License and Usage

Please follow the original licenses, access terms, and citation requirements of the corresponding public datasets and upstream sources when using these files.
