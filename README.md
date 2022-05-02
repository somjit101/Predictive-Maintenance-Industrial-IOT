# Predictive-Maintenance-Industrial-IOT
Illustrating a typical Predictive Maintenance use case in an Industrial IoT Scenario. By using Statistical Modelling and Data Visualization we attempt to perform Failure Analysis and Prediction of crucial industrial equipments like Boilers, Pumps, Motors etc. so that necessary actions can be taken by the management for their repair, servicing and optimal performance.


## About the [Dataset](https://www.kaggle.com/nphantawee/pump-sensor-data)
* Contains 220314 readings by 51 sensors taken at an interval of 1 minute over a period of 5 months for a large-scale industrial pump. 
* Each sensor makes some important measurement used to determine the working condition of the pump, like vibration, operative voltage, current drawn, heat generated, RPM etc.
* The column 'machine_status' indicates the current working condition of the pump. If it is 0, it indicates that the pump is working as expected. If it is 1, the pump is malfunctioning and needs repair. 

## Objective 
Given the past and current set of sensor readings **predict failure of the pump**. 

### Exploratory Data Analysis :
On Performing EDA, a lot of multi-collinearity among the sensor readings is observed and we get a clear understanding of the distribution of the sensor readings and how correlated they are amongst themselves. We notice a clear patch of high dependency values in the Correlation Matrix. 

### Prediction Model Used : 
Decision-Tree based Classifier

#### Details about the file : [Repair_Sensor_Deviations.xlsm](Sensor_Data_EDA/Repair_Sensor_Deviations.xlsm)
Here, we filter out only those rows from the dataset where the pump is malfunctioning/needs repair status. Then we subtract the mean value of individual sensor readings during the 'normal' working condition of the pump from the respective columns. Thus, we obtain the deviations of the sensor readings from the normal means for each timestamp where the pump is malfunctioning. The values have been color-coded and we clearly see the sensors with highest entropy contributing to the decision boundary of classification and those which do not contain any useful intelligence for predictive maintenance and can be dropped. 
