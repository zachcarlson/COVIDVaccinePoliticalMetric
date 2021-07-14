
# Assessing Proportion of Fully Vaccinated Individuals in Red States Versus Blue States Using a Political Metric

## Project Overview

This repository was created for the DSCI 521 course at Drexel University. The overall scope of this project was to see whether or not red states versus blue states had different proportions of fully vaccinated individuals based off a political metric.  The political metric was calculated using [election data](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/42MVDX) going back to 1976, provided by the [MIT Election Lab](https://electionlab.mit.edu/).  The [COVID data](https://github.com/owid/covid-19-data/tree/master/public/data) was pulled from [Our World In Data](https://ourworldindata.org) at time of processing on **June 1st, 2021**.

## File Manifest: 

- `RedBlueStates_ZACH.ipynb` - Main code that calcualtes political metric and analyzes COVID data.
- `Folder /data` - Contains all data files 
  - `states.csv` - Names and abbreviations of all states
  - `election_results.csv` - Election data from 1976-2020 (source in **Project Overview**)
  - `election_results_FINAL.csv` - Cleaned version of election_results.csv
  - `us_state_vaccinations.csv` - US COVID data (source in **Project Overview**)
- `DSCI 521 Final Presentation.pptx` - PowerPoint slides for final presentation, includes analyses from three other avenues of inquiry (See **Team Members**)
 
## Reason for Project:
This project was completed on June 1st, 2021.  At the time, COVID was still on the rise.  Even still, knowing how states are responding to the pandemic is critical for us to respond quickly and efficiently in the future.  Political sentient clearly plays a role in the everyday citizen's view of the pandemic.  We were curious as to whether rhetoric from the Trump Administration - or from the Republican party as a whole - had any impact on which individuals were getting vaccines.

## Team Members

Our team consisted of the following individuals: 

- Julie Scheffler, anz27@drexel.edu
- Srijan Pandey, sys39@drexel.edu
- Fernando Ramirez, wm374@drexel.edu
- Zach Carlson, zc378@drexel.edu

Our overall project was broken down into four separate avenues of inquiry, all of which related to COVID data.  My portion (Zach), pertained to election data.  While group members are listed above, **VaccinePoliticalMetric was entirely my work.**

## Requirements
- Python ≥ 3.8. 
- Python modules, packages, and methods required: 
    - `pandas`
    - `matplotlib.pylot`
    - `numpy`
    - `scipy`

## How to Execute Code: 

All of the code in this project needs to be opened with the Jupyter notebook environment. We recommend using [Anaconda](https://www.anaconda.com/products/individual) to help with Jupyter notebook.  Additionally, this code can be run in Google Colab or your preferred Python coding environment, assuming folder organization remains unchanged.

## Explanation of Code: 

### _**Political Metric**_

To sort each state in red versus blue, we took the historical election data and gave each state either a `1` or a `-1` based on if it voted Republican or Democrat for a given election year.  We added these values up to get a rough idea of political sentiment.  A value of `12` would be the most Republican, a value of `-12` would the most Democratic (the election data spanned 12 election cycles).  

To utilize the historical election data, several things had to be addressed:
1. If just the 2020 election results were used swing states may be placed into the incorrect political group.  
2. If all election years are used equally, states that were historically red but are currently very blue may be marked as perfectly neutral (i.e. California).

To address these concerns, all election years were used (solves issue 1) and a list of `weights` were applied to the `1`s and `-1`s, giving more weight to more recent elections compared to older ones.

The states were then sorted based off if they were greater than 0 (i.e. voted majority Repulican since 1976) or less than 0 (i.e. voted majority Democrat since 1976).


## Known Limitations of Project:

- The project sorts states based off Presidential election data only.  It would be worthwhile to look at more local elections, Senate elections, etc.
- The findings are purely correlation.  It simply plots/sorts states based off Presidential-based election data against the proportion of people fully vaccinated.  It does not take into account number of vaccines available, number of vaccination sites available, the average distance a person is to a vaccinate site, the manufacturer's available in each area, the free time a state's citizens have to get vaccines, marketing budget in each state, etc.
