# ASDGC-Dataset

Benchmark datasets for multivariate time series forecasting, used in the study **Adaptive-scale dynamic graph learning with cross-scale global fusion for non-stationary time series forecasting (ASDGC)**.

This repository provides eight benchmark datasets and documents their archive files, statistics, data formats, extraction instructions, and original sources.

## Repository contents

```text
ASDGC-Dataset/
├── ETTm1.zip
├── ETTm2.zip
├── exchange_rate.zip
├── illness.zip
├── weather.zip
├── solar-energy.zip
├── PEMS04.zip
├── PEMS07.zip.001
├── PEMS07.zip.002
├── README.md
└── DATA_SOURCES.md
```

## Dataset inventory

| Dataset | Variables | Time steps | Frequency | Domain |
| --- | ---: | ---: | --- | --- |
| ETTm1 | 7 | 69,680 | 15 min | Electricity transformer temperature |
| ETTm2 | 7 | 69,680 | 15 min | Electricity transformer temperature |
| Exchange-Rate | 8 | 7,588 | Daily | Economy |
| Weather | 21 | 52,696 | 10 min | Meteorology |
| Solar-Energy | 137 | 52,560 | 10 min | Energy |
| ILI | 7 | 966 | Weekly | Public health |
| PEMS04 | 307 | 16,992 | 5 min | Traffic |
| PEMS07 | 883 | 28,224 | 5 min | Traffic |

## Data format

Each extracted data file is a comma-separated numeric matrix:

- Rows correspond to time steps.
- Columns correspond to variables, sensors, or time series.
- Files contain numeric values only.
- Files have no header row.

## Extracted data files

The extracted files can be organized in a local data directory as follows:

```text
datasets/
├── ETTm1/ETTm1.txt
├── ETTm2/ETTm2.txt
├── exchange_rate/exchange_rate.txt
├── illness/illness.txt
├── weather/weather.txt
├── solar-energy/solar-energy.txt
├── PEMS04/PEMS04.txt
└── PEMS07/PEMS07.txt
```

Directory and file names are case-sensitive on Linux.

## Download and extraction

Download the required archives from this repository and extract them to a local directory.

### PEMS07 split archive

The PEMS07 archive consists of two parts:

- `PEMS07.zip.001`
- `PEMS07.zip.002`

Download both parts into the same directory and merge them in the order shown below before extraction.

**Linux/macOS**

```bash
cat PEMS07.zip.001 PEMS07.zip.002 > PEMS07.zip
unzip PEMS07.zip
```

**Windows Command Prompt**

```bat
copy /b PEMS07.zip.001 + PEMS07.zip.002 PEMS07.zip
```

After merging on Windows, extract the resulting `PEMS07.zip` with an archive utility.

## Original and upstream sources

The principal dataset access points are:

| Dataset | Original or upstream source |
| --- | --- |
| ETTm1 and ETTm2 | [ETT dataset](https://github.com/zhouhaoyi/ETDataset) |
| Exchange-Rate and Solar-Energy | [Multivariate time series benchmark data](https://github.com/laiguokun/multivariate-time-series-data) |
| Weather | [Jena weather data](https://www.bgc-jena.mpg.de/wetter/) |
| ILI | [CDC FluView](https://gis.cdc.gov/grasp/fluview/fluportaldashboard.html) |
| PEMS04 and PEMS07 | [Caltrans PeMS](https://pems.dot.ca.gov/) |

Additional source notes and archive-to-file mappings are provided in [`DATA_SOURCES.md`](DATA_SOURCES.md).

The datasets remain associated with their original providers, citations, access conditions, and reuse requirements. Please consult the original sources for the applicable terms and attribution requirements.

## Citation

When using this collection:

1. Cite the ASDGC article associated with these benchmark datasets.
2. Cite the original dataset sources or associated publications as appropriate.
3. Record the version or commit of this dataset repository to identify the data used.

## Corrections

Please use GitHub Issues to report missing files, extraction problems, incorrect source information, or inconsistencies in dataset statistics and file descriptions.
