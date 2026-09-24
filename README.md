# PROGRAMMING ASSIGNMENT 4
### GREFALDEO, Lettice Hyacinth P. | 2ECE-C

This repository contains Python scripts designed to solve the different problems given in ECE 2112, Programming Assignment 4. Below is a summary of each script

```python
import pandas as pd

#load excel file to notepook
board = pd.read_excel("board2.xlsx")

#compute for the average and display the table
board["Average"] = board[["Math", "GEAS", "Electronics"]].mean(axis=1)
board
```

**Output:**

<img width="807" height="671" alt="image" src="https://github.com/user-attachments/assets/67aa21b8-16c4-4205-8623-c39d5beab6cb" />
<img width="807" height="435" alt="image" src="https://github.com/user-attachments/assets/27d1010c-0b26-49fb-bd01-ccc70bcb9139" />


## **PROGRAMMING PROBLEMS**

### A. Visayas Communication Dataframe

```python
VisComm = board[(board['Hometown'] == 'Visayas') & (board['Track'] == 'Communication')].copy()

#output the following elements of the data frame only
VisComm[['Name', 'Gender', 'Math', 'Electronics', 'Average']]
```

**Output:**

<img width="417" height="215" alt="image" src="https://github.com/user-attachments/assets/384dc256-dd3f-4616-8b78-f886e4baa347" />


### B. Visayas Female Dataframe

```python
VisFemale = board[(board['Hometown'] == 'Visayas') & (board['Gender'] == 'Female')].copy()

#calculate the average
VisFemale['Average'] = VisFemale[['Math','Electronics','GEAS','Communication']].mean(axis=1)

#store rows with averages 60 and above only
VisFemale = VisFemale[VisFemale['Average'] >= 60]

#output the following elements of the data frame only
VisFemale[['Name', 'Track', 'GEAS', 'Electronics', 'Average']]
```

**Output:**

<img width="460" height="183" alt="image" src="https://github.com/user-attachments/assets/5f5b50fb-fd4c-4956-a6e1-5fa70591646a" />


### C. Category-Average Visualization 

```python
import matplotlib.pyplot as plt 

#compute mean per track, genderm hometown
means = {
    "Track": df.groupby("Track")["Average"].mean(),
    "Gender": df.groupby("Gender")["Average"].mean(),
    "Hometown": df.groupby("Hometown")["Average"].mean()
}

colors = ["skyblue", "yellow", "pink"]

#plot
plt.figure(figsize=(15,4))

for i, ((key, value), color) in enumerate(zip(means.items(), colors), 1):
    plt.subplot(1,3,i)
    value.plot(kind='bar',color = color)
    plt.title(f"Average by {key}")
    plt.xlabel(key)
    plt.ylabel("Average")

plt.tight_layout()
plt.show()
```

**Output:**

<img width="1687" height="453" alt="image" src="https://github.com/user-attachments/assets/d458cc7b-f187-4193-8301-6278465d9cda" />

