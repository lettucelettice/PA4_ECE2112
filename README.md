# PROGRAMMING ASSIGNMENT 4
### GREFALDEO, Lettice Hyacinth P. | 2ECE-C

This repository contains Python scripts designed to solve the different problems given in ECE 2112, Programming Assignment 4. Below is a summary of each script

```python
import pandas as pd

#load excel file to notebook
board = pd.read_excel("board2.xlsx")
board
```

**Output:**

<img width="641" height="573" alt="image" src="https://github.com/user-attachments/assets/dab5a4a8-51ed-411e-a0a7-91328ff31d1d" />

<img width="632" height="414" alt="image" src="https://github.com/user-attachments/assets/d3eb9d55-99a7-462e-aedd-0d9796763fd4" />

## **PROGRAMMING PROBLEMS**

### A. Visayas Communication Dataframe

```python
VisComm = board[(board['Hometown'] == 'Visayas') & (board['Track'] == 'Communication')].copy()

#output the following elements of the data frame only
VisComm[['Name', 'Gender', 'Math', 'Electronics']]
```

**Output:**

<img width="318" height="212" alt="image" src="https://github.com/user-attachments/assets/4cb1b2b4-bb7e-4380-89e6-763dedcd4ddf" />


### B. Visayas Female Dataframe

```python
VisFemale = board[(board['Hometown'] == 'Visayas') & (board['Gender'] == 'Female')].copy()

#calculate the average
VisFemale['Average'] = VisFemale[['Math','Electronics','GEAS','Communication']].mean(axis=1)

#store rows with averages 55 and above
VisFemale = VisFemale[VisFemale['Average'] >= 60]

#output the following elements of the data frame only
VisFemale[['Name', 'Track', 'GEAS', 'Electronics', 'Average']]
```

**Output:**

<img width="480" height="173" alt="image" src="https://github.com/user-attachments/assets/f5642cbd-8e5e-4c3e-a493-f09afd5b6ae8" />

