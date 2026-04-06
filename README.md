# ASDGC-Dataset

This repository provides the benchmark datasets used in the experiments of **Adaptive-Scale Dynamic Graph Learning with Cross-Scale Global Fusion (ASDGC)** for non-stationary multivariate time series forecasting.

This repository is intended for **academic reproducibility and research convenience**. It is **not** an official distribution channel for the original datasets.

## Repository Contents

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

## Important Note for PEMS07

Due to repository file-size constraints, **PEMS07** is split into two archive parts:

- `PEMS07.zip.001`
- `PEMS07.zip.002`

Merge the two parts before extraction.

### Linux / macOS

```bash
cat PEMS07.zip.001 PEMS07.zip.002 > PEMS07.zip
unzip PEMS07.zip
```

### Windows (Command Prompt)

```bat
copy /b PEMS07.zip.001 + PEMS07.zip.002 PEMS07.zip
```

## Data Format

After extraction, each dataset is stored in **plain-text `.txt` format**.

- Each file is a numeric matrix.
- Rows correspond to time steps.
- Columns correspond to variables, sensors, or series.
- The data can be loaded directly in Python or similar scientific-computing environments.

### Example

```python
import numpy as np

x = np.loadtxt('your_dataset.txt', delimiter=',')
print(x.shape)  # [T, N]
```

## Dataset Statistics

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

## Dataset Overview

- **ETTm1 / ETTm2**: Electricity Transformer Temperature datasets with 7 variables sampled every 15 minutes.
- **Exchange-Rate**: Daily exchange rates of 8 countries.
- **Weather**: 21 meteorological variables sampled every 10 minutes.
- **Solar-Energy**: Solar power generation from 137 plants sampled every 10 minutes.
- **ILI**: Weekly influenza-like illness ratios.
- **PEMS04 / PEMS07**: Large-scale traffic benchmarks commonly used in spatio-temporal forecasting.

## Suggested Directory Layout

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

## Upstream and Benchmark References

- TimeSeriesDatasets benchmark collection:[TimeSeriesDatasets benchmark collection](https://github.com/juyongjiang/TimeSeriesDatasets)
- ETT dataset / Informer: [ETT dataset / Informer](https://github.com/zhouhaoyi/ETDataset)
- Common multivariate forecasting benchmark collection: [Common multivariate forecasting benchmark collection](https://github.com/laiguokun/multivariate-time-series-data)
- Weather dataset source: [Weather dataset source](https://www.bgc-jena.mpg.de/wetter/)
- ILI source (CDC FluView): [ILI source (CDC FluView)](https://gis.cdc.gov/grasp/fluview/fluportaldashboard.html)
- Traffic benchmark preprocessing reference: [Traffic benchmark preprocessing reference](https://github.com/guoshnBJTU/ASTGNN/tree/main/data)

## Notice on Data Ownership and Use

- This repository is provided for **academic research and reproducibility**.
- The original datasets remain the property of their respective providers or rights holders.
- This repository does **not** claim ownership of third-party datasets.
- Users are responsible for complying with the original dataset licenses, citation requirements, access conditions, and redistribution rules.
- If any included material should not be redistributed, please contact the repository maintainer for review or removal.

## Citation

If you use this repository in academic work, please:

​	Cite the **original dataset papers, websites, or upstream repositories** when required.

## Repository License Scope

Unless otherwise stated, any license attached to this repository applies only to the repository author's own materials, such as the README text, scripts, and repository-specific notes. It does **not** automatically apply to third-party datasets.
