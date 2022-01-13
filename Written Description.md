***The Top 5 Stations With The Most Daily Entries in NYC***

Nia Clark
#

**Abstract**
##
The objective of this project was to use exploratory data analysis to provide insight on where urgent care center, City MD, should place COVID-19 testing sites around NYC. I worked with the MTA turnstile dataset in order to find the top 5 stations that received the most daily entries and by using this information, City MD will be able to place testing sites in front of these stations with the assumption that more people will mean more demand for COVID tests. With the use of SQL and Python, I was able to clean the dataset as well as create tables and graphs to showcase my results.


**Design**
##
City MD is a healthcare company founded in 2010 and operates more than 150 urgent care centers in New York and New Jersey. It is the largest urgent care company in the New York Metro area. Due to the new Omicron variant, COVID infection rates have been spiking all over the city. To aid in stoping the spread, City MD wants to set up COVID-19 testing sites outside of NYC subway stations that receive the most daily entries in efforts to be exposed to as many people as possible with the assumption that more people would mean more demand for a COVID test. Analyzing the MTA turnstile data would identify which subway stations receive the most traffic. The focus was analyzing the data for the months October through December of 2021, because it is the holiday season and a lot of people would be traveling.


**Data**
##
The MTA turnstile dataset contains weekly turnstile data for every NYC subway station dating back to May of 2010. The MTA publishes a CSV every week, and each CSV is an observation for a moment in time for a specific turnstile. The CSV's contain readings that occur every 4 hours and has columns, C/A, for contral area, UNIT, for remote unit of a station, SCP, for subunit channel position, the station name, the linename for all train lines that can be boarded at that station, DIVISION, DATE, the time for a scheduled audit event, DESc, the cumulative entry register value for a device, and lastly the cumulative exit register value for a device. This dataset, although informative, is very messy, as some of the turnstiles are counting down, not up, which caused anomylies in the data.


**Algorithm**
##
This data exploration began with loading turnstile data for the months of October through December into python using SQLAlchemy. From there, SQL was used to create a table for all 3 months. The python methods, .columns, .strip(), and .title(), were used to reformat the column names. Next, the data was grouped by each turnstile group that belonged to each station. In order to find daily entries for each station during each week, the columns "Previous_Date" and "Previous_Entries" were created which allowed for the subtraction of the Previous_Entries column from the Entries column to find how many people enetered each station daily. As previously stated, some turnstiles counted in reverse, whcih led outliers in the data. To mitigate this, the data was filtered so that the max counter for a turnstile was 100,000. Summing each station's daily entries and ranking them resulted in the top 5 stations with the most daily entries. From there, each station was analyzed individually and the date where each station received the most entries can be pinpointed.


**Tools**
##
* SQLAlchemy used to facilitate communication between Python databases 
* Pandas and Numpy for data cleaning 
* Matplotlib for data visualization 


**Communication**
##
After conducting this analysis, the top 5 stations City MD should focus on is 34th st Penn station, PATH New World Trade Center, Thirty st, 34th st Herald Square, and 42 st Grand Central. Observed from the data for 34th st Penn station, there was a spike in entries the week of October 14th, so City MD should have more Covid tests on hand for October. PATH New World Trade Center had several spikes in entries, with the highest being the week of October 22. Entries drastically increased several times throughout the three months, so City MD should be prepared for a lot of people at that station needing tests. Thirty st also had various spikes throughout the three months, with the highest entries being on the week of  December 12. It seems that entries rise the beginning of each month, so City MD should expect that. 34th st Herald Square's data fluctuated the most. The beginning and end of each month had high entries, while the middle of the month entries dropped. City MD should consistently have a high number of tests available for that station. Lastly, Grand Central station experienced a spike in entries the week of November 16, while the pattern of entries stayed consistent for October and December. City MD should expect to conduct more tests than usual mid-November. These results will be presented through slides and visualizations.





