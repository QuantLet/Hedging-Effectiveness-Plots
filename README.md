[<img src="https://github.com/QuantLet/Styleguide-and-FAQ/blob/master/pictures/banner.png" width="888" alt="Visit QuantNet">](http://quantlet.de/)

## [<img src="https://github.com/QuantLet/Styleguide-and-FAQ/blob/master/pictures/qloqo.png" alt="Visit QuantNet">](http://quantlet.de/) **Hedging Effectiveness Plots** [<img src="https://github.com/QuantLet/Styleguide-and-FAQ/blob/master/pictures/QN2.png" width="60" alt="Visit QuantNet 2.0">](http://quantlet.de/)

```yaml

Name of Quantlet: 'Data and Codes of Hedging Cryptos with Bitcoins Futures'

Published in: 'Hedging Cryptos With Bitcoin Futures'

Description: 'This repository archives the data and codes to produce the results of paper Hedging Cryptos with Bitcoin Futures.'

Keywords: 'Optimal hedge ratio, risk measures, BTC future, BTC, futures contract'

Author: 'Anonymous for double blind peer reviewed'

Submitted:   '6 Jan 2022'
```

## Generate Results Files
To generate the results files, one needs to run the following python scripts with the same configuration file as input
src/calibration.py
src/get_OHR.py
src/get_HEs.py.
The python scripts should be run in the exact order above to generate correct results.

One can generate results with other datasets, following are the steps to do so
prepare the data according to the format and file structure in processed_data
prepare a configuration json file
Run the three python scripts above using the configuration file in the second step, e.g.
calibration.py --config configs/BBT_future_Tiingo_ltc_MM.json
get_OHR.py --config configs/BBT_future_Tiingo_ltc_MM.json
get_HEs.py --config configs/BBT_future_Tiingo_ltc_MM.json

Configuration file is a json file with fields describe as follows
data_name: the name of the dataset in the processed_data folder, e.g. BBT_future_BITW20
spot_name: column name of the spot’s log return in each data file, e.g. log return BITW20
future_name: column name of the futures’ log return in each data file, e.g. log return future
calibration_method: MM stands for method of moments; MLE stands for maximum likelihood
q_arr: the quantile level used by MM. This field will not affect MLE, but it cannot be empty.
k_ERM: Risk aversiveness of exponent risk measure being used as loss function while searching for the optimal hedge ratio
q_arr_ES: quantile level of expected shortfall being used as loss function
q_arr_VaR: quantile level of value-at-risk being used as loss function
h_Clip: range of optimal hedge ratio

## Generate Plots in Papers
The figures and tables in the paper are generated from the Jupyter Notebook files in Pynotebooks/figures and Pynotebooks/tables respectively.
