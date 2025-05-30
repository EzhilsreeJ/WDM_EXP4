### EX4 Implementation of Cluster and Visitor Segmentation for Navigation patterns
### AIM: 
To implement Cluster and Visitor Segmentation for Navigation patterns in Python.
### Description:
<div align= "justify">Cluster visitor segmentation refers to the process of grouping or categorizing visitors to a website, 
  application, or physical location into distinct clusters or segments based on various characteristics or behaviors they exhibit. 
  This segmentation allows businesses or organizations to better understand their audience and tailor their strategies, marketing efforts, 
  or services to meet the specific needs and preferences of each cluster.</div>
  
### Procedure:
1) Read the CSV file: Use pd.read_csv to load the CSV file into a pandas DataFrame.
2) Define Age Groups by creating a dictionary containing age group conditions using Boolean conditions.
3) Segment Visitors by iterating through the dictionary and filter the visitors into respective age groups.
4) Visualize the result using matplotlib.

### Program:
```python
import pandas as pd
import matplotlib.pyplot as plt

# Load the dataset
visitors_df = pd.read_csv("clustervisitor.csv")  # Insert the file path to your CSV file

# Define age groups
age_groups = {
    'Young': (visitors_df['Age'] <= 30),
    'Middle-aged': ((visitors_df['Age'] > 30) & (visitors_df['Age'] <= 50)),
    'Elderly': (visitors_df['Age'] > 50)
}

# Print visitors in each age group
for group, condition in age_groups.items():
    visitors_in_group = visitors_df[condition]
    print(f"Visitors in {group} age group:")
    print(visitors_in_group)
    print()


```
### Output:

### Visualization:
```python
# Count visitors in each age group
visitors_counts = []
for group, condition in age_groups.items():
    visitors_in_group = visitors_df[condition]
    visitors_counts.append(len(visitors_in_group))

# Plot the distribution of visitors across age groups
age_group_labels = list(age_groups.keys())
plt.figure(figsize=(8, 6))
plt.bar(age_group_labels, visitors_counts, color='skyblue')
plt.xlabel('Age Groups')
plt.ylabel('Number of Visitors')
plt.title('Visitor Distribution Across Age Groups')
plt.show()
```
### Output:
![Screenshot 2025-04-12 141557](https://github.com/user-attachments/assets/7f6dd90d-10c9-446d-aa5e-62e72112f251)
![Screenshot 2025-04-12 141605](https://github.com/user-attachments/assets/69d7f9ca-c5b1-48c7-b8f6-45109d63ae85)


### Result:
Thus the Implementation of Cluster and Visitor Segmentation for Navigation patterns is executed successfully.
