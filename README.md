
# Assessing Proportion of Fully Vaccinated Individuals in Red States Versus Blue States Using a Political Metric

## Project Overviews

This repository was created for the DSCI 521 course at Drexel University. The overall scope of this project was to see whether or not red states versus blue states had different proportions of fully vaccinated individuals based of a political metric.  The political metric was calculated using [election data](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/42MVDX) going back as far as 1976.  The [COVID data](https://github.com/owid/covid-19-data/tree/master/public/data) was pulled from Our World In Data at time of processing on **June 1st, 2021**.

## File Manifest: 

- `final_project.ipynb` - Main code that scrapes the Tesla website
- `Database_Checker.ipynb` -  Main code used for Tesla and Federal comparison
- `Folder /data` - Contains all data files 
  - `tesla_superchargers.csv` - Tesla dataset created after running code
  - `alt_fuel_stations (Oct 4 2020).csv` [Federal dataset](https://afdc.energy.gov/stations/#/analyze?country=US&fuel=ELEC&ev_levels=all&access=public&access=private) copy
  - `output.json` Initial JSON output for proof of concept, final version will *not* output this file.
- `Folder /drafts` - Contains code versions used to scrape Tesla website
  - `10-11-2020.ipynb` - First version of code used for scraping
  - `Project 11-16-2020.ipynb` - Second version
  - `Project 11-23-2020.ipynb` - Third version 
- `Tesla Data Project Presentation.pptx` - PowerPoint slides for final presentation
 
## Reason for Project:
This project was completed in May 2021.  At the time, COVID was still on the rise.  Even still, knowing how states are responding to the pandemic is critical for us to respond quickly and efficiently in the future.  Political sentient clearly plays a role in the everyday citizen's view of the pandemic.  We were curious as to whether rhetoric from the Trump Administration - or from the Republican party as a whole - had any impact on which individuals were getting vaccines.

## Team Members

Our team consisted of the following individuals: 

- Julie Scheffler, anz27@drexel.edu
- Srijan Pandey, sys39@drexel.edu
- Fernando Ramirez, wm374@drexel.edu
- Zach Carlson, zc378@drexel.edu

## Requirements
- This project was developed using Python 3.8. 
- Python modules, packages, and methods required: 
    - `pandas`
    - `matplotlib.pylot`
    - `numpy`

## Results of Code:

After running the code, the resulting dataset is found in two main formats. In Python, the data structure of the results is a nested dictionary file type that is written out to a `.csv` file. In addition, outside of Python, a local `.csv` file is created after code execution. 

## How to Execute Code: 

All of the code in this project needs to be opened with the Jupyter notebook environment. We recommend using [Anaconda](https://www.anaconda.com/products/individual) to help with Jupyter notebook.

## Explanation of Code: 

### _**Political Metric**_

To sort each state in red versus blue, we took the historical election data and gave each state either a `1` or a `-1` based on if it voted Republican or Democrat.  We added these values up to get a rough idea of political sentiment.  A value of `12` would be the most Republican, a value of `-12` would the most Democratic.  

This idea made sense in theory, but required several major tweaks.
1. By equating the election results of 1976 to 2020, states that were historically red but are currently very blue were marked as perfectly neutral (i.e. California.)



## Known Limitations of Project:

- The project is limited to the collection of data only from Tesla’s website, not including any other electric vehicle. 
- Consumers cannot use our project to check for locations of other types of electric vehicles, only Tesla Supercharger locations.
- The federal dataset information used is time dated to the time of download. The last download of the dataset was: October 4th 2020
- The `Database_Checker` is limited to user input of: State, City, and Zip Code - between the datasets.


## Potential Future Development: 




## Sharing Permissions:

- Content is free to share and copy for own use.
 



