# Deer and other NYC Animals
## Goals
My goal with this first Lede project was to find out where people spot deer in New York City, along with other wild animals more associated with rural or suburban places. I wanted to know where these deer were hanging out and what other perhaps animals New Yorkers saw. I was hoping to create a fun map of where animals were found.
***
*Notebook for analysis: [animal reports.ipynb](https://github.com/cassidyjen/animal-reports-project/blob/main/animal%20reports.ipynb)
- Original dataset is the Urban Park Ranger Animal Condition Response from [NYC Open Data](https://data.cityofnewyork.us/Environment/Urban-Park-Ranger-Animal-Condition-Response/fuhs-xmg2/about_data)
- The data dictionary is also uploaded [here](https://github.com/cassidyjen/animal-reports-project/blob/main/UrbanParkRangerAnimalConditionResponse_DataDictionary_20181107.xlsx)
### CSV files for the following:
- All species but with one column containing relevant address information for geocoding: [animals_with_locations.csv](https://github.com/cassidyjen/animal-reports-project/blob/main/animals_with_locations.csv).
- Only the deer reports, including coordinates: [deer_cleaned.csv](https://github.com/cassidyjen/animal-reports-project/blob/main/deer_cleaned.csv)
- All animals but with cleaned up species names:[valid_species.csv](https://github.com/cassidyjen/animal-reports-project/blob/main/valid_species.csv)
- Most common animals by borough [top_animals.csv](https://github.com/cassidyjen/animal-reports-project/blob/main/top_animals.csv)
- The top 20 most common properties where animals were reported [properties.csv](https://github.com/cassidyjen/animal-reports-project/blob/main/properties.csv).
***
## Findings
The NYC Department of Parks and Recreation has a [delightful dataset](https://data.cityofnewyork.us/Environment/Urban-Park-Ranger-Animal-Condition-Response/fuhs-xmg2/about_data) on NYC Open Data with information about "requests for animal assistance, relocation, and/or rescue completed by the Urban Park Rangers." According to the data dictionary, "Requests are typically made by other Parks staff, park visitors making requests in person, and by calls to 311. Each record represents a single request." This dataset had a wealth of information about where people were reporting various animals. There are more than 8,000 individual animals in the dataset, which spans from May 2018 to June 2024. It also contains some limited location information and information about what happened to the request (what did the ranger have to do, essentially) and the condition of the animal. NYC Open Data also has another dataset with information about 311 requests for wildlife, which didn't end up being very useful for my purposes.
## Data analysis
Most of my work involved organizing and cleaning the data using pandas. Fortunately, it was a pretty clean dataset. The dataset has inconsistent location information, sometimes as vague as "near trash can", instead of coordinates or street addresses. I attempted to combine an additional NYC dataset of 311 calls to add additional location information (most crucially, coordinates), but there wasn’t enough overlap (such as an ID number) that I felt I could confidently match entries between the two after experimenting. Instead, I geocoded the addresses using the park property and borough, so all map locations are approximate. I was able to filter and sort the data I did have to try to answer some questions, including:
1) What animals are people seeing and reporting to urban rangers?
2) Where are these animals (which properties?)
3) Where are the deer, specifically? What sort of shape are they in?
4) What animal was most common in each borough?
## Skills and approaches
 I used pandas for cleaning, sorting and analyzing the data. I did some geocoding and made maps and charts using Datawrapper. The process of trying and failing different methods was great practice. I hit a limit with Nominatim after trying to geocode about 900 locations with Nominatim, so I wonder if the Google Maps API would've given me better results. I pivoted and only mapped the deer as opposed to all animals, which was probably easier to view anyway. This was my first time creating a website with HTML/CSS, so I relied heavily on templates. 
 ## If I had more time
This deer map is incomplete, because as far as I can tell some northern portions of city parks (maybe not technically in the Bronx) are not showing up on the boroughs map of NYC that Datawrapper provides. I tried to play around with a map of the NYC Parks, but it was too large for Datawrapper to accept even afte trying to simplify it in using mapshaper. Ideally I would use another software to try to get a more complete underlying map and determine a better way to map coordinates. The CSS/HTML on the site is a bit lazy, so ideally I would’ve spent more time on the design aspects of it, maybe adding more photos. The map itself could be more beautiful. I also would've liked to create a fun illustration for the most common animal for each borough (at least as fun as a symbol for a dead fish can be).
