# CMPU250 Project Repo
 Domestic violence reporting and analysis by Ash Todd, Nora Phelan, Eaint May and Zack Taylor 

## Table of Contents
* [Codebook](#CodeBook)
  - [Used Variables Table](#Used-Variables)
  - [Created Variables Table](#Created-Variables)
## CodeBook

### Used Variables

| Variable | Description |
| --- | --- |
| Suspect Race | Race of the suspect in an IPV report |
| Victim Race | Race of the victim in an IPV report |
| Suspect Age | Age of the suspect in an IPV report |
| Victim Age | Age of the victim in an IPV report |
| Precinct Code | Precinct in which the IPV report took place |

### Created Variables

| Variable | Description |
| --- | --- |
| Suspect-Victim Age Gap | Difference between the age of the suspect and the victim in an IPV report (Positive val indicates the suspect is older, negative val indicates the victim is older) |
| Felony Offense | Binary indicating whether a felony offense was described in an IPV report (1 indicates felony) |
