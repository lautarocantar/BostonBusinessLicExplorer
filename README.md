# BostonBusinessLicExplorer

### Introduction:
There are multiples variables that make up the business environment of a city and different analysis might want to focus on a different aspect of it. For example, if we are analyzing the evolution of restaurants in a particular neighborhood or the ownership of each business is local or non-local, we would have two different problems to solve: it would require the researcher several queries or filters until he or she has the desired subset and then it would have to map it. 
The Boston Business Licenses Explorer is an interactive tool that allows researchers and policy makers to analyze the Boston Business Licenses dataset from different perspectives in multilayer analysis. The user can select what subset of the original dataset he or she wants to analyze and the tool will map it and provide some information about the evolution in a histogram.

### Data source:
The City of Boston has provided to the Boston Area Research Initiative (BARI) a dataset with information for issued Business and Non-Business Licenses since the year 2007. The full dataset consists of 292,060 cases and 35 variables. For the current project, only 48.336 observations were used, those that meet the following criteria:

*	Belong to Business Licenses that have been classified either as “Alcohol”, “Food”, “General Business Licenses”, “Self-serving stations”, “Recreational” and “Entertainment”.
*	Were active between 2012 and 2016.
*	There are complete records of latitude and longitude.

The resulting dataset was merged with another BARI’s dataset to have for each observation the following columns:

*	Individual level
*	Census tract level
*	Neighborhood level

Once that the dataset had all the relevant information, the following data processing activities were done:

*	If a license had a contact ZIPCODE that belongs to Boston, it is assumed that that license was “LOCAL” and those that did not meet that criteria were “NON-LOCAL”.
*	It is assumed that the “START.DATE” of a license was the year that that license started to be active and the “END.DATE” the year that ceases to be active.
*	A new subset was created for all the unique businesses, no matter if they had one license or many licenses registered. 
*	If the license had in its description “RENEW” or anything that referred to being a renewal, it was marked that license as a renewal.


### Application:

Link to the application: https://boston-bl.shinyapps.io/App-1/

The application has the following features:

*	“Select Year” filter: with this filter, the user can select which particular year he wants to analyze. The histogram and the map will react to the selected year. Only those licenses issued between 2012 and 2016 were considered for this analysis.
*	“Select Analysis level” filter: with this filter, the user can focus on a particular analysis level: Local licenses, non-local licenses, renewed licenses, issuances, expirations and unique businesses. Each option has a description associated with it, that provides some context to the user.
*	“Select Level” filter: with this filter, the user can see the data at the individual levels or aggregated at census tract or neighborhood levels.
*	“Select Business Category” level: with this filter, the user can select which business category wants to explore. These categories are the result of a unification process to make the data more understandable: there are many different kinds of business licenses that the City of Boston issues: there are more than 20 categories only for alcohol selling.
This is an image of what the application looks like:
 
### Tools:
The main tool used was R and the “Shiny” package.

### Future:
There are some modifications that could be done to the current project.
Firstly, is to eliminate the double definition of the Business Categories: one in the histogram and later in the dropdown. It would be an important feature if by selecting one column of the histogram the visualization has the same effect than selecting the dropdown. 
Secondly, some information about the history of each category will be added in the upcoming new version of the project.
