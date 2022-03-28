# Predict-accident-risk-score-for-unique-postcode
MachineHack hackathon
According to IBEF “Domestic automobiles production increased at 2.36% CAGR between FY16-20 with 26.36 million vehicles being manufactured in the country in FY20.Overall, domestic automobiles sales increased at 1.29% CAGR between FY16-FY20 with 21.55 million vehicles being sold in FY20”.The rise in vehicles on the road will also lead to multiple challenges and the road will be more vulnerable to accidents.Increased accident rates also leads to more insurance claims and payouts rise for insurance companies.

In order to pre-emptively plan for the losses, the insurance firms leverage accident data to understand the risk across the geographical units e.g. Postal code/district etc.

In this challenge, we are providing you the dataset to predict the “Accident_Risk_Index” against the postcodes.Accident_Risk_Index (mean casualties at a postcode) = sum(Number_of_casualities)/count(Accident_ID)

Working example:

Train Data (given)	 	 
Accident_ID	Postcode	Number_of_casualities
1	AL1 1JJ	2
2	AL1 1JP	3
3	AL1 3PS	2
4	AL1 3PS	1
5	AL1 3PS	1
Modelling Train Data (Rolled up at Postcode level)	 
Postcode	Derived_feature1	Derived_feature2	Accident_risk_Index
AL1 1JJ	_	_	2
AL1 1JP	_	_	3
AL1 3PS	_	_	1.33
The participants are required to predict the 'Accident_risk_index' for the test.csv and against the postcode on the test data.

Then submit your 'my_submission_file.csv' on the submission tab of the hackathon page.

Pro-tip: The participants are required to perform feature engineering to first roll-up the train data at postcode level and create a column as “accident_risk_index” and optimize the model against postcode level.

Few Hypothesis to help you think: "More accidents happen in the later part of the day as those are office hours causing congestion"

"Postal codes with more single carriage roads have more accidents"

(***In the above hypothesis features such as office_hours_flag and #single _carriage roads can be formed)

Additionally, we are providing you with road network data (contains info on the nearest road to a postcode and it's characteristics) and population data (contains info about population at area level). This info are for augmentation of features, but not mandatory to use.

The provided dataset contains the following files: 

# Train: 4,84,042 rows x 27 columns
# Test: 1,15,958 rows x 27 columns
train.csv & test.csv:

'Accident_ID',
'Police_Force',
'Number_of_Vehicles',
'Number_of_Casualties',
'Date',
'Day_of_Week',
'Time',
‘Local_Authority_(District)',
'Local_Authority_(Highway)',
'1st_Road_Class',
'1st_Road_Number',
'Road_Type',
'Speed_limit',
'2nd_Road_Class',
'2nd_Road_Number',
'Pedestrian_Crossing-Human_Control',
'Pedestrian_Crossing-Physical_Facilities',
'Light_Conditions',
‘'Weather_Conditions',
'Road_Surface_Conditions',
'Special_Conditions_at_Site',
'Carriageway_Hazards',
'Urban_or_Rural_Area',
'Did_Police_Officer_Attend_Scene_of_Accident',
'state',
'postcode',
'country'
# Population: 8,035 rows x 10 columns
population.csv:

​​'postcode',
'Rural Urban',
'Variable: All usual residents; measures: Value',
'Variable: Males; measures: Value',
'Variable: Females; measures: Value',
‘Variable: Lives in a household; measures: Value',
‘Variable: Lives in a communal establishment; measures: Value',
'Variable: Schoolchild or full-time student aged 4 and over at their non term-time address; measures: Value',
'Variable: Area (Hectares); measures: Value',
'Variable: Density (number of persons per hectare); measures: Value'
# Road Network: 91,566 rows x 8 columns
roads_network.csv:

'WKT',
'roadClassi',
‘roadFuncti',
'formOfWay',
'length',
'primaryRou',
'distance to the nearest point on rd',
'postcode’
