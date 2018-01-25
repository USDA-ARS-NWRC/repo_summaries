![Overview Image](docs/_static/ModelSystemOverview_AWSM.png?raw=true)

## Core Software

### AWSM
Automated Water Supply Model (AWSM) was developed at the USDA Agricultural
Research Service (ARS) in Boise, ID. AWSM was designed to streamline the
workflow used by the ARS to forecast the water supply of multiple water basins.
AWSM standardizes the steps needed to distribute met. data with SMRF, run an
energy and mass balance with iSnobal or PySnobal, and process the results,
while maintaining the flexibility of each program.
* Automated & streamlined water supply forecasts
* Manages modules to perform each task

### Weather Inputs
Weather inputs include meteorologic station data, gridded Weather Research and
Forecasting Model (WRF) forecast data, and data from other atmospheric models.  
Met. station weather data can be automatically downloaded and stored with the
[WeatherDatabase](https://github.com/USDA-ARS-NWRC/WeatherDatabase) tool.
Gridded weather models can be downloaded with the
[weather_forecast_retrieval](https://github.com/USDA-ARS-NWRC/weather_forecast_retrieval)
tool. This data is used as input for SMRF.

### SMRF
Spatial Modeling for Resources Framework (SMRF) was developed by Dr.
Scott Havens at the USDA Agricultural Research Service (ARS) in Boise, ID.
SMRF was designed to increase the flexibility of taking measured weather data
and distributing the point measurements across a watershed. SMRF was developed
to be used as an operational or research framework, where ease of use,
efficiency, and ability to run in near real time are high priorities.
* Distributes met. database
* Flexible and efficient
* Allows new models and functionality

### iSnobal/ PySnobal
iSnobal is a gridded energy-balance snowmelt model. It predicts storage,
runoff, and other snow state parameters. iSnobal is driven by the gridded
forcing data like the data output from SMRF. PySnobal is a Python wrapped
implementaion of iSnobal to allow for closer integration with other models
and more run-time flexibility within the code.

### SNOWAV
Snow and Water model Analysis and Visualization (SNOWAV) was designed to
standardize the processing of basin hydrologic summary information. SNOWAV
summarizes total basin storage and change in storage, basin water inputs, and
the state of basin snow-pack. SNOWAV generates succinct reports that include
spatial distribution visualization and summary tables.
* Analytics and insights
* Spatial distribution visualizations
* Summary reports

## Additional Software

### IPW
Image Processing Workbench (IPW) is a collection of utilities to process digital
images. IPW conatins the energy-balance models Snobal and iSnobal.

### WeatherDatabase
WeatherDatabase downloads and stores met. station data in an SQL database. It
has the capability to maintain a raw data table, an auto cleaned data table,
and a manually cleaned data table. This data can be read into SMRF for
distribution over a specific domain.  

### weather_forecast_retrieval
Weather forecast retrieval gathers relavant gridded weather forecasts to ingest
into physically based models for water supply forecasts

### inicheck
inicheck is a high level configuration file checker enabling developers tight
control over their users configuration files.

###  basin_setup
The basin setup tool is a python script designed to create the required inputs
for running SMRF and AWSM simulations. The tool outputs a single netcdf file
containing basin, mask, DEM, veg type and height (from Landfire), veg tau,
and veg K.
