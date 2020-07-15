# FORCE RECONSTRUCTION ML MODEL
A repository for research and development of a model for force reconstruction using strain gauges for the suspension system of a BAJA SAE vehicle.

## INPUT AND OUTPUT

The expected data is, at the most basic level, timeseries data with several different channels which measure voltage. The applied load is recorded and incorporated in the data as the targets for the model.

Depending on testing, several architectures could be used, and depending if the time dependent aspect of it is important or not (static / dynamic load). 

For the sample data from 2018, the input data seems to be very simply just a single value at a single load. With this type of data the best option is likely to use multivariate regression, such as XGBoost. 

If we find a way to generate time-dependent data for training the model, then regression will not be enough. For that case something like a LSTM/RNN would be necessary at some level. This is a much, much harder problem and both the data generation and processing would be more involved, and likely time consuming. [A newly developed architecture](https://arxiv.org/abs/2002.10253) might be of great help in this case,  where physics are incorporated in the deep learning model to reduce the amount of data needed to train it and reduce the possibility of overfitting. 

## STRAIN GAUGE LOCATIONS

To make sure the data is usable for the model, locations on the suspension arm that are "sensitive" to certain force directions are going to be selected. These points that are more sensitive are valuable because they ensure that the data fed to the model has more information about the load state and that it is not drowned out by noise.

## SIMULATED DATA

To create a prototype of the model, it is valuable to have data that can be easily fed into the model to ensure it is working as intended. [This dataset](https://www.kaggle.com/daalgi/fem-simulations) could be valuable to start with. Ideally, after a while it would be also good to maybe generate some synthetic data either through ANSYS or a mathematical model that better represents our problem. Then it should progress to training the model with real world data either from a simplified problem such as the rod we have or directly from the suspension. 

## LICENSE

There is no license provided as of now. All rights are reserved to current and future members of the University of Calgary Schulich Off-Road BAJA student team. Contact one of the members of the team for inquiries and requests.