# SafeTrax-GPS-Based-Vehicle-Analytics- 
We have to perform EDA, Data Engineering and Unsupervised ML Clustering to find any hidden Patterns among Data attributes and if we can leverage it to make any operational optimization <br>

# About Data : 
The data we receive is in a csv with each row as a OrdDict([]). The data is generated by a GPS tracker installed on Fleet of SafeTrax. There are almost 6 Million data points covering Tracker info from almost 200 Unique Trackers installed on Vehicles. <br>

## Features : <br>
------------------------------------------------------------------------------------------------------------------- <br>
'oid' : Unique Id for each data packet sent to Cloud from Tracker <br>

'vehicleId' : Unique Identifier assigned to each vehicle(missing for many in datasets). <br>

'coordinates' : List of Latitude and Longitude for the data packet generated by hardware. <br>

'speed' : Speed of Vehicle in Kmph. <br>

'imei' : Unique IMEI number of Cellular SIM installed on each Tracker. <br>

'cabCode' : Number Plate of each Vehicle(Missing for many). <br>

'insertionTimeString' : Time at which data is registrered at Cloud. <br>

'timeString' : Timestamp of moment at which data is generated. <br>

'deltaDistance' : Distance(in Kms) covered in between current and last data packed sent on cloud. <br>

"siteName'" : Name of Site/Client. <br>

'course' : Compass Value(ranging from 0 to 359 for degrees) for the vehicle's heading/direction for the respective data packet. <br>

'mainPower' : If the main power or Vehicle ignition is On/Off. <br> 

'vehicleColour' : Color of Vehicle. <br>

'odometerDistance' : Total Distance covered by the tracker/vehicle after it was installed. <br>

'fwVersion': Firmware Version of Hardware. <br>

'address' : Address of Location from where data packet was generated by tracker. <br>

'cached' : If the data was directly sent or was not sent(probably because of Loss of Cellular Network Connectivity) <br>

-------------------------------------------------------------------------------------------------------------------
# Our approch to the problem:

# Step 1 : Import Data which is in format of OrderedDict per row in csv and convert it to Pickle file 
### File : (Data Convert and Merge into a single Pickle File.ipynb)
We will use csv sniffer to import data of each row as a slice and perform basic NLP data cleaning tast upon it. Upon completion we will again convert it back to Pickle file to be later used by other functions/files.

# Step 2 : Import Pickle File aand perform basic EDA :  Univariate, Bi-Variate Analysis GPS Data w.r.t. other features in data 
### File : (FastTrax_EDA_25GBRAM.ipynb)
We will perform basic EDA on all features and drop any irrelevant columns which can't affect the outcome of any possible models we will deploy on them

# Step 3 : Unsupervised ML : Clustering with KMeans Clustering
### File : (Creating and Visualizing Clusters in Data_25GBRAM.ipynb)
We will perform Clsuetring on feature Engineered data we received from previous step/file
