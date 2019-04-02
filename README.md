# Capstone-project-2
	
		
		Safety is very important in any neighborhood, mostly we consider safety by looking at crime rate in a neighborhood. One of the aspects of safety that we should be considered is rate of incidents(like fire, stuck in elevators, gas leaking etc.) or facilities in a house to prevent these type of incident, facilities in fire departments in neighborhoods and how quick fire departments response to an incident, these could be considered as safety rate of a place as well. My goal is to find safety of neighborhoods based on the mentioned aspects, and mark neighborhoods safe or unsafe which can help house seekers to find a better one and  real state agencies to give a better guide to their clients, also local consults to pay more attention to fire departments’ problems in their neighborhood to improve safety. 
	The data set is taken from data.cityofnewyork.us, which has Fire_Box of departments, Type of incident, Time of arrival and …


Here is description of some features:
Incident_Datetime; The date and time of the incident.
First_Onscene_Datetime; The date and time of the first unit at the scene of the incident.
First_Assignment_Datetime; The date and time of the first unit assignment.
Incident_Response_Second; The elapsed time in seconds between the incident_datetime and the first_onscene_datetime.
Incident_Response_Travel; The elapsed time in seconds between the first_assignment_datetime and the first_onscene_datetime.
INCIDENT_CLOSE_DATETIME; The date and time that the incident was closed in the dispatch system.
 I will use the features to determine safety of neighborhoods in New York City in five boroughs by making a predictive model and test it on my training set to score the accuracy of the model and finally select the best one. It will label zip codes as of safe and unsafe. 
The final result will be delivered in papers with codes in jupyter notebook for wrangling and exploratory of the data and also explanations of the predictive model for the problem with appropriate slides deck to present a better story. 
	Exploratory is a key factor in working with a dataset and it starts off getting shape , info , finding and filling missing values. The data set is big( over 2 million observations) therefore it is better start it with less rows, I chose 10000. As many datasets, there are missing values in my dataset, by having deep look, I realized that they are because of type of incidents which means the incidents are assigned to a fire department and the department realized that it should be taken care by other departments like a medical center or a police department therefore other features related to it were null and I dropped them.
	Time is very important in any fire department, how fast they respond to an incident, how quick they close an incident , these can be  keys to determine how a fire department handle and control incidents. So I made feature name “total_time that tells us how long each incident take to be cared and cleared and I made it by subtracting “FIRST_ON_SCENE” column from “INCIDENT_CLOSE_TIME” column. (of course after converting it to datetime format). By plotting the new column we realize fraction of time consuming which is mostly under 10000 seconds.
 	As I digging in the dataset, I realized that I need more feature to get a better result so I added another data set, ‘Population’, which can improve predictive model. So merge two data frames would be the best choice. And made another feature “ratio_per_capita” that shows ratio of incident in each zip code based on the population and would be a key variable to determine how quick a fire department respond to incidents. 
	But I should do one more thing before starting modeling the data frame and it is making a target variable; by defending a function that determine safe or unsafe of a zip code, if in any zip code ratio_per_capita is higher than 0.001 and total_time is higher than the mean then we consider the zip code as unsafe and if either one happens in a zip code then it would consider as safe. Here is the link for jupyter file of codes in my project; https://drive.google.com/file/d/1TRmckEST7c5eJcu95OdRM_RtZL0rCdT5/view? usp=sharing 
Conclusion:
	After trying models like, Logisticregression, RandomForest, and GradientBoosting, the performance of Logisticregression is the best. 94 percent accuracy.
	And the ranking feature shows that, the consuming time for each incident, response time and the facilities of departments are important factors to determine safety of a neighborhood, therefore in order to improve the safety, fire departments should address their needs like more trucks, engines to make their response time faster, also they should be in cooperate to city consults and municipal authorities in order to improve the traffic and roads in order to make shorter the response time of the incident.
We may need more data like the season, temperature of incident time to make a better model and conclusion but based on what I was working on, I would conclude having more fire department with more facility in unsafe zip codes and improving roads for fire trucks to make them a faster response can be important matters that consult cities should pay attention to.
