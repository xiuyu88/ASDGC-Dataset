# Data Sources for ASDGC Experiments

This file records the upstream access points and experiment-ready file names used by the ASDGC project. It complements the repository README and should be updated whenever the data files or preprocessing procedure change.

| Dataset | ASDGC archive | Extracted file expected by code | Upstream access point | Notes |
|---|---|---|---|---|
| ETTm1 | `ETTm1.zip` | `ETTm1/ETTm1.txt` | `https://github.com/zhouhaoyi/ETDataset` | Electricity Transformer Temperature benchmark, 15-minute sampling |
| ETTm2 | `ETTm2.zip` | `ETTm2/ETTm2.txt` | `https://github.com/zhouhaoyi/ETDataset` | Electricity Transformer Temperature benchmark, 15-minute sampling |
| Exchange-Rate | `exchange_rate.zip` | `exchange_rate/exchange_rate.txt` | `https://github.com/laiguokun/multivariate-time-series-data` | Daily exchange-rate benchmark |
| Weather | `weather.zip` | `weather/weather.txt` | `https://www.bgc-jena.mpg.de/wetter/` | Meteorological benchmark, 10-minute sampling |
| Solar-Energy | `solar-energy.zip` | `solar-energy/solar-energy.txt` | `https://github.com/laiguokun/multivariate-time-series-data` | Solar power benchmark, 10-minute sampling |
| ILI | `illness.zip` | `illness/illness.txt` | `https://gis.cdc.gov/grasp/fluview/fluportaldashboard.html` | Weekly influenza-like illness ratios |
| PEMS04 | `PEMS04.zip` | `PEMS04/PEMS04.txt` | `https://pems.dot.ca.gov/` | Processed traffic-flow benchmark from PeMS data |
| PEMS07 | `PEMS07.zip.001` and `PEMS07.zip.002` | `PEMS07/PEMS07.txt` | `https://pems.dot.ca.gov/` | Split archive; merge before extraction |
