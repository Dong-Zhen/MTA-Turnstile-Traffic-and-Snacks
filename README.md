# MTA-Turnstile-Traffic-and-Snacks

# Project Idea
For my mta turnstile project I will be reaching out to a non-existant nonprofit company called Yolocal Snack. They sell affordable traveler snacks supplied by the local food community to New York City commuters. Yolocal Snack aims to help local food communities make revenue and make commuters happy by solving their energy and hunger problems. According to [geotab](https://www.geotab.com/time-to-commute/), 90% of NYC residents' commute take longer than 1 hour. A lot can change for commuters emotionaly and physically within that time frame especially if they were in a rush to get to their destinations during meal hours and missed their meals. 

**Potential Business Ideas**
- Future store locations near top stations commuters enter during weekday meal hours
- To find ways to handle demand, they'd like to know if there are "rush hours" at these stations, when enters/exits far exceeds average enters/exits

**Additional Info**
## Yolocal Snack
### 546 9th Avenue Brooklyn, New York
#### Energizing commuters with traveler snacks made by vendors within YOUR LOCAL COMMUNITY
1. Vegetable, Meat, Mixed Snack Bags $3 each
2. Bottled Water, Bottled Coffee $1 each
3. Chocolate Bar and Hard Candy $1 for 2 
#### Profits go back to the community. Prepay through our App for quick pickup. 

# Project email

To: YoLocal Snack Executives, Rita and Leon

I visited your store last week and picked up a vegetable snack bag. I really enjoyed the sweet potato hashbrowns inside, it gave me the energy to work through the morning. Due to that experience and my desire to help the community, I want to contribute towards Yolocal Snack's vision of energizing commuters with locally made traveler snacks. With my data science background, I could prepare a report for you by the end of next week that will help you identify the top stations where New Yorkers with long commutes exit and enter from. Within the report, you can also find visualizations of four-hour-time windows when you could expect a rush of people leaving or entering those stations. These insights could help Yolocal Snack find new locations to open shops and better prepare for higher demands during certain time frames. I attached a project proposal in the email, please let me know if you are interested and if you have any questions. Looking forward to hearing back from the team. 

# Project Proposal 

Objective: Use MTA's public Turnstile Data to help YoLocal Snack expand into communities with stations that New Yorkers enter and exit for long daily commutes. Determine when "rush hours" are to prevent overcrowded shops and to fully meet demands.  

Datasets: MTA's Turnstile Data, Dataset that has location of stations
Resources Required: Mta train schedule to estimate how long commutes are from stations within Queens or Brooklyn to Manhattan, or a study based on new york city commute time. 
Domain Knowledge: Learn if fast food sellers near potential stations receive more customers during meal hours, Know Habits of New York Commuter(I have a decade of transit commuting observations), mta person who uploads the mta data  
Tools: SQL, Python libraries: Pandas, Numpy, Matplotlib, Seaborn
Algorithms: TBH

Step1: Store datasets into SQL Database 
Step2: Pull SQL tables into Python
Step3: Clean data in Python
Step4: Perform Exploratory Data Analysis
Step5: Plot and Visualize Data

Conclusion: Since most New Yorkers work from 9am to 5pm EST, there is potential for Yolocal Snack to fill in their hunger and thirst needs. My analysis and visualizations will reveal which stations within each borough receive the most commuters on weekdays,determine whether or not most New Yorkers commute during meal hours and present a rough estimate of how long commutes take for commuters within stations. 




## Brainstorm - Feel Free to look this over before our meeting Rita and Leon
Steps: 
1. Storing Data in SQL Database
2. Data Cleaning in Python
- Remove white spaces in column
- Delete column Division and DESC
- Should I remove rows of data with Entries of ten 0's? I notice they are often associated with a certain scp. Might require domain or expert knowledge here
  -If I do there might be gaps in data between observatoins because the exit is still counting
-Combine station and linename for unqiue identifier
  - what use do I have for columns c/a,unit,scp? maybe add c/a or unit to station,linename concat
-After having a unique indentifer, check for duplicates, then delete
-Check nulls, then delete
-Calculate the 4 hour time window entry and exit by subtracting latest time by earlier time
  -group time into 4 hour time windows like this? 0:0 - 4:0
- check for inconsistencies within dataframe
- merge location of station dataset with current?
3. Exploratory Data Analysis
- Display 2 dataframes, sort by most exits and entries during hours 8-12. Check if other time ranges exist within morning breakfast hours
  -Visualize the stations with most exits and entries in 2 scatter plots during hours 8-12
  -color code location of stations. red for brooklyn, blue for queens etc
- check where most new yorkers are between morning (8-12) and evening (4-8) hours 
  - note majority of exits between 8-4
  - use this info to determine where most commuters travel to since the morning
  - this can help give an rough estimate of distance traveled and commute time
  - maybe help determine a potential market for high school and college students and unionized handiman workers who leave work during this time(this can be saved for another data exploration, our goal is majority of 9-5workers)
- Display dataframes of most exit and entries during evening hours 4-8.
  - Learn potential locations to sell light snacks and liquids during travels back home. goal is to find the best station locations to sell both morning and evening snacks to commuters. make the most impact with available resources. 
- Can visualize the number of commuters for each stations by tracking exits from 4pm-12am and entries from 6am-12pm.

Datachecks- analyze data from 2019 then compare to 2020 to see if stations are the same for both year
