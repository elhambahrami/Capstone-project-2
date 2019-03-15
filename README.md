# Capstone-project-2
	
		
	Safety is very important in any neighborhood, mostly we consider safety by looking at crime rate in a place. One of the aspects of safety that we should be considered is rate of incidents(like fire, stuck in elevators, gas leaking etc.) or facilities in a house to prevent these type of incident, facilities in fire departments in  neighborhoods and how quick  fire departments response to an incident, these could be considered to rate safety of a place as well. My goal is to find safety of neighborhoods based on the mentioned aspects, and mark neighborhoods safe or unsafe which can help seekers house to find a better one and  also real state agencies to give a better guide to their clients and also local consults to address problems in their neighborhood to improve safety.
	The data set is taken from data.cityofnewyork.us, which has Fire_Box of departments, Type of incident, Time of arrival and …
	I will use the features to determine safety of neighborhoods in New York City in five boroughs by making a predictive model and test it on my training set to score the accuracy of the model and finally select the best one. It will label neighborhoods as of safe and unsafe.
	The final result will be delivered in papers with codes in jupyter notebook for wrangling and exploratory of the data and also explanations of the predictive model for the problem with appropriate slides  deck to present a better story.





	Exploratory is a key factor in working with a dataset and it starts off getting shape , info , finding and filling missing values. The data set is big( over 2 million observations) therefore it is better start it with less rows, I chose 10000.  As many datasets, there are missing values in my dataset, by having deep looking at it I realized that they were because of type of incidents which means the incidents are assigned to a fire department and the department realized that it should be taken care by other departments like a medical center, therefore other features related to it were null and I dropped them, but missing values in ‘ZIPCODE’ column were different so I used  random choice function to fill it. 
	Here are features that I am going to use and their definition;
Incident_Datetime; The date and time of the incident.
First_Onscene_Datetime; The date and time of the first unit at the scene of the incident.
First_Assignment_Datetime; The date and time of the first unit assignment.
Incident_Response_Second; The elapsed time in seconds between the incident_datetime and the first_onscene_datetime.
Incident_Response_Travel; The elapsed time in seconds between the first_assignment_datetime and the first_onscene_datetime.
Dispatch_Response_Second; The elapsed time in seconds between the incident_datetime and the first_assignment_datetime.
Starfire_Incident_ID
Incident_Classification
	Another thing is outliers which effect predictive models, so by defining a function, Remove_Outlier_Indices, I improve it. Also some features are not useful for the goal of the project, so feature engineering helps making new and better ones out of them, using group by and aggregation functions, make it possible. As I digging in the dataset, I realized that I need more feature to get a better result so I added another data set, ‘Population’, which can improve predictive model. So merge two data frames would be the best choice. 
	But I should do one more thing before starting modeling the data frame and it is making a target column. Function ‘binning’ does it for my dataset and now it is the time to try different algorithm to find a best model.
