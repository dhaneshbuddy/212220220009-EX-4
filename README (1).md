# Ex-04-Datascience
### AIM:
To perform various operations of multivariate analysis in the given dataset.

### ALGORITHM:
A dataset("SuperStore.csv") is given , use that and perform the multivariate operations in the colab and get the output in graph models.

### Program:
```
Developed by : SANJAY S
Reg no : 212222230132
```
import pandas as pd 
import seaborn as sns
import matplotlib as plt
df = pd.read_csv("SuperStore.csv")
print(df)

df.corr()

print(sns.scatterplot(df["Postal Code"]))

sns.barplot(x = df['Postal Code'], y=df['Sales'],data = df)

GRAPH = df.loc[:,['Region','Sales']]
GRAPH=GRAPH.groupby(by=["Region"]).sum().sort_values(by="Sales")
sns.barplot(x=GRAPH.index,y="Sales",data=GRAPH)

plt.xlabel=("Region")
plt.ylabel=("Sales")

df.info()
df.describe()

GRAPH = df.loc[:,['Postal Code','Sales']]
GRAPH=GRAPH.groupby(by=["Postal Code"]).sum().sort_values(by="Sales")
sns.barplot(x=GRAPH.index,y="Sales",data=GRAPH)

plt.xlabel=("Postal Code")
plt.ylabel=("Sales")

sns.barplot(x = df['Postal Code'], y=df['Sales'],hue = df['Region'])

sns.heatmap(df.corr(),annot=True)
