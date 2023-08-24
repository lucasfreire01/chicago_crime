# Greetings people 🖖
This project is called Chicago_crime, and the goal is to predict the efficacy of police in Chicago. The crime rate at Eua coming up in the least years in relation to 2021 Chicago gets 43% more crime incidents, Calculating the police efficacy can show the problem that can be resolved and down this statistic. The dataset has data from 2001 to currently  on a total of 695976 rows and 19 columns, these columns are Case Number, Date, Block, IUCR, Primary Type, Description, Location Description, Arrest, Domestic, Beat, District, Ward, Community Area, FBI Code, X Coordinate, Y Coordinate, Latitude, Longitude, Location.
 
| Variable Name         | Description                                                |
|-----------------------|------------------------------------------------------------|
| Case Number           | Unique identifier for a specific criminal case.           |
| Date                  | Date and time when the incident occurred.                 |
| Block                 | Block address or location of the incident.                |
| IUCR                  | Illinois Uniform Crime Reporting code. Link bellow.         |
| Primary Type          | Primary category of the reported crime.                   |
| Description           | Description of the specific crime.                        |
| Location Description  | Description of the location where the incident occurred.  |
| Arrest                | Indicates whether an arrest was made.                     |
| Domestic              | Indicates whether the incident is domestic-related.        |
| Beat                  | Police beat where the incident occurred.                  |
| District              | Police district where the incident occurred.              |
| Ward                  | Ward of the city where the incident occurred.             |
| Community Area        | Community area where the incident occurred.               |
| FBI Code              | Code from the FBI's National Incident-Based Reporting System (NIBRS). |
| X Coordinate          | X-coordinate of the incident location on a map.           |
| Y Coordinate          | Y-coordinate of the incident location on a map.           |
| Latitude              | Latitude of the incident location.                        |
| Longitude             | Longitude of the incident location.                       |

Link IUCR description: https://data.cityofchicago.org/Public-Safety/Chicago-Police-Department-Illinois-Uniform-Crime-R/c7ck-438e

The dataset consists of various data types, including float, int, boolean, and str, distributed across different columns. All types of data will be treated to check the best columns will do a feature select, pre_process, and train the model. As mentioned earlier, our primary goal is to predict the efficacy of police. By mapping the efficacy of police in Chicago, we can help police authorities take the best decisions based on your efficacy from last year.


# Feature Selection
Now We go to select the useful We going to explain the motion that deletes some columns:
Ps: All columns were deleted because don't have competently value for this project.<br>
     
  **Case Number**<br>
  The identification of features doesn't is necessary.

  **Block**<br>
  This feature report alike of address with a zip code close we prefer to use just neighborhoods because we get the same result covering specific address in large regions(neighborhoods) For this we get a specific column with neighborhoods.

  **IUCR**<br>
  This column reports crime codes in Chicago We decided to take off this column because there is another column with these codes translated for names of crimes. If you check up will see a link to the IUCR link description There is a table explaining each code and your mind. This table is seen this.<br>
| IUCR | PRIMARY DESCRIPTION       | SECONDARY DESCRIPTION       | INDEX CODE | ACTIVE | 
|------|---------------------------|-----------------------------|------------|--------| 
| 110  | HOMICIDE                  | FIRST DEGREE MURDER         | I          | Yes    | 
| 130  | HOMICIDE                  | SECOND DEGREE MURDER        | I          | Yes    | 
| 141  | HOMICIDE                  | INVOLUNTARY MANSLAUGHTER    | N          | Yes    | 
| 142  | HOMICIDE                  | RECKLESS HOMICIDE           | N          | Yes    | 
| 261  | CRIMINAL SEXUAL ASSAULT   | AGGRAVATED - HANDGUN        | I          | Yes    | 
| 262  | CRIMINAL SEXUAL ASSAULT   | AGGRAVATED - OTHER FIREARM  | I          | Yes    | 
| 263  | CRIMINAL SEXUAL ASSAULT   | AGGRAVATED - KNIFE          | I          | Yes    | 
| 264  | CRIMINAL SEXUAL ASSAULT   | AGGRAVATED - OTHER DANGEROUS| I          | Yes    | 
| 265  | CRIMINAL SEXUAL ASSAULT   | AGGRAVATED - OTHER          | I          | Yes    | 
| 266  | CRIMINAL SEXUAL ASSAULT   | PREDATORY                   | I          | Yes    | 
| 271  | CRIMINAL SEXUAL ASSAULT   | ATTEMPT AGGRAVATED          | I          | Yes    | 
| 272  | CRIMINAL SEXUAL ASSAULT   | ATTEMPT AGGRAVATED          | I          | Yes    | 
| 273  | CRIMINAL SEXUAL ASSAULT   | ATTEMPT AGGRAVATED - KNIFE  | I          | Yes    |
| 110  | HOMICIDE                  | FIRST DEGREE MURDER         | I          | Yes    | 
| 130  | HOMICIDE                  | SECOND DEGREE MURDER        | I          | Yes    | 
| 141  | HOMICIDE                  | INVOLUNTARY MANSLAUGHTER    | N          | Yes    | 
| 142  | HOMICIDE                  | RECKLESS HOMICIDE           | N          | Yes    | 
| 261  | CRIMINAL SEXUAL ASSAULT   | AGGRAVATED - HANDGUN        | I          | Yes    | 
| 262  | CRIMINAL SEXUAL ASSAULT   | AGGRAVATED - OTHER FIREARM  | I          | Yes    | 
| 263  | CRIMINAL SEXUAL ASSAULT   | AGGRAVATED - KNIFE / CUTTING| I          | Yes    | 
| 264  | CRIMINAL SEXUAL ASSAULT   | AGGRAVATED - OTHER DANGEROUS| I          | Yes    | 
| 265  | CRIMINAL SEXUAL ASSAULT   | AGGRAVATED - OTHER          | I          | Yes    | 
| 266  | CRIMINAL SEXUAL ASSAULT   | PREDATORY                   | I          | Yes    | 
| 271  | CRIMINAL SEXUAL ASSAULT   | ATTEMPT AGGRAVATED - HANDGUN| I          | Yes    | 
| 272  | CRIMINAL SEXUAL ASSAULT   | ATTEMPT AGGRAVATED - OTHER  | I          | Yes    |<br>

How can you see the primary description in the dataset originally called primary type in IUCR There are some cases for example 041A and 041B it's the same crime but with secondary descriptions is different.

**Description**<br>
This description is the secondary description in the table up don't is necessary because we get the primary description in the dataset original The second description will be used because we have information more important in other columns.

**Domestic**<br>
We have a column called Local Description that reports some values (street, residence, other, Sidewalk) This column is related to abuses, domestic violence and etc. We just know if is residence, street, and others because of this impact on the police efficacy.

**Beat**<br>
This column has the number of police vehicles the efficacy and the number of police vehicles don't relate.

**District**<br>
This column has the number of police districts we studying this column because there are some cities that have more police districts for each neighborhood or one police district for more than one neighborhood. In Chicago's case, there is just one police district for each neighborhood but has inconsistent values for example -121 does not exist in a district with this code we think is a specific place. We don't have information about these abnormal values but the dataset has a column called ward which has the district code right.

**Community Area**<br>
In the community where there was an incident, the focus is to use the neighborhood so the community we can't get because we have information better then.

**FBI Code**<br>
This FBI Code reports a system in the FBI with code mind the incidents. We get a column with the incidents so don't this column

**X Coordinate, Y Coordinate, Latitude, Longitude, Location**<br>
We have the district in Chicago these columns aren't as useful as said before we have neighborhoods telling us the location. There is a specific in these columns the x, and y coordinates we don't need specific action but a region.

Feature Used
---
**Date**<br>
This column has the date of rows and information on features This is important because it gives us insights into there is varying numbers of cases in different parts of the year. Also as we have dates of many years maybe using this column we get some defaults.

**Primary Type**<br>
The primary type reports the names of incidents.

**Location Description**<br>
This column is important because based on the location maybe there is a varying in police efficacy. Using this information we can get a graph to have a better vision of the police efficacy.

**Arrest**<br>
Target column this column will tell us the efficacy. Join all datas predicts we have a answer to our problem(Goal of the project)

**Ward**<br>
This column has the number of each neighborhood. We prefer to use this column because we'd like a large region and don't have a specific location with this choose we make it the goal but computationally cheap.
![Map Numer Chicago](https://github.com/lucasfreire01/chicago_crime/blob/main/clearmap1.jpg)<br>
This Image show the number of the neighborhood in Chicago exactly the numbers in the column.

**NOTE**
This dataset is very large and I can't get with all datasets so I split into two parts the first part of model training and the second the test.
