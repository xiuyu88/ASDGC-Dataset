# ASDGC-Dataset

Benchmark data companion for **Adaptive-Scale Dynamic Graph Learning with Cross-Scale Global Fusion for Non-Stationary Time Series Forecasting (ASDGC)**.

## Companion repositories

| Research artifact                 | GitHub repository                                            | Responsibility                                               |
| --------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Benchmark data and source notes   | [xiuyu88/ASDGC-Dataset](https://github.com/xiuyu88/ASDGC-Dataset) | Experiment data files, dataset statistics, source information, and extraction instructions |
| Model code and experiment scripts | [xiuyu88/ASDGC](https://github.com/xiuyu88/ASDGC)            | Model implementation, environment setup, training, evaluation, and reproduction commands |



## Scope

This repository provides the preprocessing-ready benchmark files used by the ASDGC experiments and documents the file names, expected directory layout, statistics, and upstream sources.

It is a research-reproducibility companion to the ASDGC code repository. It is not intended to replace the official dataset providers. The datasets remain associated with their original providers, citations, access conditions, and reuse requirements. Users should consult and cite the original sources listed below.

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

| Dataset       | Variables | Time steps | Frequency | Domain                              |
| ------------- | --------: | ---------: | --------: | ----------------------------------- |
| ETTm1         |         7 |     69,680 |    15 min | Electricity transformer temperature |
| ETTm2         |         7 |     69,680 |    15 min | Electricity transformer temperature |
| Exchange-Rate |         8 |      7,588 |     Daily | Economy                             |
| Weather       |        21 |     52,696 |    10 min | Meteorology                         |
| Solar-Energy  |       137 |     52,560 |    10 min | Energy                              |
| ILI           |         7 |        966 |    Weekly | Public health                       |
| PEMS04        |       307 |     16,992 |     5 min | Traffic                             |
| PEMS07        |       883 |     28,224 |     5 min | Traffic                             |

## Data format

After extraction, each ASDGC input is a comma-separated numeric matrix:

- rows correspond to time steps;
- columns correspond to variables, sensors, or series;
- files contain numeric values only;
- files have no header row.

Example:

```python
import numpy as np

x = np.loadtxt("dataset/ETTm1/ETTm1.txt", delimiter=",")
print(x.shape)  # (time_steps, variables)
```

## Expected local layout for the code repository

Copy or extract the files into the `dataset/` directory of the ASDGC code repository:

```text
ASDGC/
└── dataset/
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

## PEMS07 split archive

Because the PEMS07 archive is split into two parts, merge the parts before extraction.

Linux/macOS:

```bash
cat PEMS07.zip.001 PEMS07.zip.002 > PEMS07.zip
unzip PEMS07.zip
```

Windows Command Prompt:

```bat
copy /b PEMS07.zip.001 + PEMS07.zip.002 PEMS07.zip
```

Windows PowerShell:

```powershell
$parts = "PEMS07.zip.001", "PEMS07.zip.002"
$out = [System.IO.File]::Create("PEMS07.zip")
foreach ($part in $parts) {
    $bytes = [System.IO.File]::ReadAllBytes($part)
    $out.Write($bytes, 0, $bytes.Length)
}
$out.Close()
Expand-Archive PEMS07.zip -DestinationPath PEMS07
```

## Original and upstream sources

Detailed source notes are provided in [`DATA_SOURCES.md`](DATA_SOURCES.md). The principal access points are:

- ETT dataset: `https://github.com/zhouhaoyi/ETDataset`
- Exchange-Rate and Solar-Energy benchmark files: `https://github.com/laiguokun/multivariate-time-series-data`
- Weather data: `https://www.bgc-jena.mpg.de/wetter/`
- ILI data: `https://gis.cdc.gov/grasp/fluview/fluportaldashboard.html`
- PeMS traffic data: `https://pems.dot.ca.gov/`

The repository records the experiment-ready files used by ASDGC. Users should cite the original dataset source or associated paper appropriate to each benchmark.

## Citation

When using this repository:

1. cite the ASDGC article;
2. cite each original dataset source required for the benchmarks used;
3. identify the matching GitHub release tag or commit when reporting a reproduction.

## Corrections

Use GitHub Issues to report missing files, extraction problems, incorrect source information, or inconsistencies between this repository and the ASDGC code repository.
