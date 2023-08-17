# Greetings people 🖖
This project is called Chicago_crime, and the goal is to predict the location of most incidents of crime in Chicago. The dataset has data from 2001 to currently  on a total of 695976 rows and 19 columns, these columns are Case Number, Date, Block, IUCR, Primary Type, Description, Location Description, Arrest, Domestic, Beat, District, Ward, Community Area, FBI Code, X Coordinate, Y Coordinate, Latitude, Longitude, Location.
 
| Variable Name         | Description                                                |
|-----------------------|------------------------------------------------------------|
| Case Number           | Unique identifier for a specific criminal case.           |
| Date                  | Date and time when the incident occurred.                 |
| Block                 | Block address or location of the incident.                |
| IUCR                  | Illinois Uniform Crime Reporting code. Dictionary.         |
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


The dataset consists of various data types, including float, int, boolean, and str, distributed across different columns. All types of data will be treated to check the best columns will do a feature select, pre_process, and train the model. As mentioned earlier, our primary goal is to predict the locations with the highest incident occurrence. By mapping these areas across Chicago, we aim to assist police authorities in effectively allocating resources and intensifying police vigilance.
