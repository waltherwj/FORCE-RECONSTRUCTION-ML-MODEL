# FORCE RECONSTRUCTION ML MODEL
A repository for research and development of a model for force reconstruction using strain gauges for the suspension system of a BAJA SAE vehicle.

## INPUT AND OUTPUT

The expected data is, at the most basic level, timeseries data with several different channels which measure voltage. The applied load is recorded and incorporated in the data as the targets for the model.

Depending on testing, several architectures could be used, and depending if the time dependent aspect of it is important or not (static / dynamic load). 

For the sample data from 2018, the input data seems to be very simply just a single value at a single load. With this type of data the best option is likely to use multivariate regression, such as XGBoost. 

If we find a way to generate time-dependent data for training the model, then regression will not be enough. For that case something like a LSTM/RNN would be necessary at some level. This is a much, much harder problem and both the data generation and processing would be more involved, and likely time consuming. [A new architecture](https://arxiv.org/abs/2002.10253) might be of great help in this case,  where physics are incorporated in the deep learning model to reduce the amount of data needed to train it and reduce the possibility of overfitting. 

## LICENSE

There is no license provided as of now. All rights are reserved to current and future members of the University of Calgary Schulich Off-Road BAJA student team. Contact one of the members of the team for inquiries and requests.