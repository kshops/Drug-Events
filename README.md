# Drug-Events
## Description of data source
The data files used for this project were drug adverse event reports downloaded from Open-FDA: https://open.fda.gov/ 
* Open-FDA has an API for real-time access, but puts a harsh limit on the number of events obtainable per request (100).
* Drug event reports were bulk-downloaded as json files for Q1 of years 2004-2014. Each file was ~1 GB in size.

## Data processing
### Adversity.ipynb was used to process data files
* Files were loaded one at a time
* Relevant fields were extracted from the json and converted into a pandas DataFrame
* DataFrames were filtered based on drug-classes of interest
* DataFrames were concatenated into a final DataFrame and saved to disk

## Visualizing the data
### First graph: 
I was interested in comparing the deaths reported for different drug classes over time. A summary table was created showing the total number of
events gropued by year, drug class, gender, and whether or not the event resulted in death. I then used Bokeh to plot graphs for each drug class showing 
deaths per year broken down by gender.

### Second graph: (inspired by gapminder.ipynb on Bokeh website)
I wanted to make a cool visualization comparing the number of deaths, total event reports, and average age of patients, oh and I wanted to show this over time.
I ended up making a scatter plot where circle size represents total number of reports with deaths and age reported on the x and y axes. A slider was used to switch
between years.

## Limitations
* Only first quarter data was used, so if there are different seasonal trends for different drugs then this may not reflect the entire picture.
* Many reports are incomplete. Filtering by reports that list drug class, gender, and age limits the sample size.
