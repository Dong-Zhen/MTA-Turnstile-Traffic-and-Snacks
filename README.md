# MTA-Turnstile-Traffic-and-Snacks

# Abstract

For my mta turnstile project I reached to a non-existant nonprofit company called Yolocal Snack. They sell affordable traveler snacks supplied by the local food community to New York City commuters. Yolocal Snack aims to help local food communities make revenue and make commuters happy by solving their energy and hunger problems. According to [geotab](https://www.geotab.com/time-to-commute/), 90% of NYC residents' commute take longer than 1 hour. A lot can change for commuters emotionaly and physically within that time frame especially if they were in a rush to get to their destinations during meal hours and missed their meals. My job as their analysis is to use public mta turnstile data to find where long distance commuters are traveling during common meal hours.

# Design 

Based of popular happy hour and breakfast times, I set the common meal hours for morning entry to be 8am - 12pm and evening exits to be 4pm - 8pm. Then I defined a commuter as a nine to five worker or student who goes to a different location on weekdays. Because it is difficult to know who is a long distance commuter, I used the subway map to identify two key variables. There's a clear distance distinction for stations that go into boroughs that is not Manhattan and stations with one or two lines.

# Data

MTA data from January 2021 to April 2021 forms the basis of my analysis. This is a good time frame to look at New York's commuter cycle. Students go back to school in January and workers resume work after major holidays. Additionally, the turnstile data has reset so it's possible to detect where anomalies begin and decide what to do with them. Decreases in commuter traffic due to COVID is not a concern because YoLocal Snack is serving New Yorkers who need to commute to work.
The MTA turnstile Data is used to find entry and exit traffic, time of day, and station and lines. I joined this data with Mta's location data to find the boroughs for each station. 

# Algorithm

After pulling in the dataset, I focused in finding and fixing the inconcsistencies within the dataset and then defining a unique identifier. After combining, the CA, UNIT, SCP, and Station together to form a unique turnstile, I was able to find and eliminate duplicates. As for the inconsistenies, I notice over 6000 unique time values which had to be reformatted to only 4 hour time windows between 12 am and 12 am. To deal with outliers, I kept only the data above the 25 quantile and below 90 quantile. Then, I had to find the entry and exit values for particular time in day using the cumulative value in the dataset. After filtering the dataframe by lines and stations outside of Manhattan, the data was ready for analysis.

During analysis, I used the top thirty top traffic stations from the filtered data to find high density stations. From these high density stations, I used the total morning entry and evening exit traffic to find the five stations with the most traffic during meal hours.   

# Tools

I used sqlite3 to store the mta turnstile and location data. Python was used to extract, clean, and analyze the data. Matplotlib and seaborn were used to plot the dataframe and visualize the results. The datetime module was used to manipulate datetime data types to aid in cleaning. 

# Conclusion

If YoLocal Snacks wants to locate by the busiest station than it would be Junction Boulevard. If they want a steady stream of commuters during morning and evening meal hours than they should locate by 77 St in Brooklyn.

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

- [Project Proposal](https://github.com/Dong-Zhen/MTA-Turnstile-Traffic-and-Snacks/blob/main/Project%20Proposal)
- [Minimum Value Product](https://github.com/Dong-Zhen/MTA-Turnstile-Traffic-and-Snacks/blob/main/Minimum%20Viable%20Project.ipynb)
- [Final Project](https://github.com/Dong-Zhen/MTA-Turnstile-Traffic-and-Snacks/blob/main/Final%20Project.ipynb)
- [Powerpoint](https://github.com/Dong-Zhen/MTA-Turnstile-Traffic-and-Snacks/blob/main/Yo-Local%20Snacks.pptx)
