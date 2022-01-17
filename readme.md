# An Open-source Model for Simulation and Corrective Measure Assessment of the 2021 Texas Power Outage

[![GitHub commit](https://img.shields.io/github/last-commit/tamu-engineering-research/2021TXPowerOutage)](https://github.com/tamu-engineering-research/2021TXPowerOutage/commits/master) &nbsp;
[![GitHub license](https://img.shields.io/badge/license-MIT-yellow)](https://choosealicense.com/licenses/mit/)


## Suggested Citation 
- Please cite the following paper when you use this data hub:  
`
Wu, Dongqi, Xiangtian Zheng, Yixing Xu, Daniel Olsen, Bainan Xia, Chanan Singh, and Le Xie. "An open-source extendable model and corrective measure assessment of the 2021 texas power outage." Advances in Applied Energy 4 (2021): 100056.
`

This paper documents the creation and improvent of this model as well as provides analyses about the reproduction and corrective measure studies of the 2021 Texas Power Outage event. The article is also available on [arXiv](https://arxiv.org/abs/2104.04146).

## Features
- Overall, this repository contains three parts: 
	1) Processed public data during the 2021 Texas Power Outage 
	2) Synethetic network that resembles the ERCOT grid
	3) Source code used to run simulated event reproduction and counterfactual analysis.


## Navigation
This data hub mainly contains five components: source data, released data, supplementary resources, parser codes, and  quick start tutorials. We navigate this data hub as follows.

- `From EIA (Generation, Demand, Demand Forecasts, and Interchange by BA)` contains public data for ERCOT, MISO and SPP as well as estimated counterfactual solar and wind generation produced by the model from Breakthrough Energy Sciences (BES). All data are in csv format and have been pre-processed to follow the same format. The first column is the name of the RTO region; The second column is timestamp when the data are sampled and the other are data values.
- `bte2k` contains the network model for Matpower. The `case_Mar3_5pm.mat` is the base model provided by BES which does not contain the additional HVDC lines and related transmission upgrades. The file `design3.mat` and `hvdc_upgraded.mat` are the models that corresponds to the new HVDC designs. `design3.mat` contains two additioal HVDC lines both conneccted to Roscoe, TX and `hvdc_upgraded.mat` contains one HVDC connection to Calfornia that is interfaced in Roscoe, TX as well as another HVDC line connected to Florida that is located in Bryan, TX.
- `code` contains the source code used to run the various simulation scenarios in the paper. The main file is `BES_winterization_derate.m` which depends on Matpower and Gurobi. With these packages installed the code can be ran directly without changing anything. The default scenario will be the reproduction of the 2021 TX Outage event which does not consider any hypothetical corrective measure. Scenarios with different combination of corrective measures can be achieved by changing the variable values in the script according to the comments.
- `data` contains additional data that are not complete or not official. It includes the various data including the `ERCOT load shed`, `ERCOT outage record` and `ERCOT load forecast` that are collected through different sources.

## Contact Us
Please contact us if you need further technical support or search for cooperation. Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.\
Email contact: &nbsp; [Le Xie](mailto:le.xie@tamu.edu?subject=[GitHub]%20TX_Outage), &nbsp; [Dongqi Wu](mailto:dqwu@tamu.edu?subject=[GitHub]%20TX_Outage), &nbsp; [Xiangtian Zheng](mailto:zxt0515@tamu.edu?subject=[GitHub]%20TX_Outage).
