# Experiment 1: EDA in IPL Dataset

## Name: RASINDHAN R

## Reg No: 212224230222

## Aim:

To perform Exploratory Data Analysis (EDA) on the IPL matches dataset and derive insights about matches per season, winning teams, toss decisions, and top venues.


## Algorithm / Procedure:

**1.Import Libraries**

  Import pandas for data handling.
  
  Import matplotlib and seaborn for visualization.
  
**2.Load Dataset**

  Use pd.read_csv() to load the IPL matches dataset.

  Check dataset shape using .shape.
  
  View first 5 rows using .head().

**3.Matches per Season (Univariate Analysis)**

  Group data by season and count matches.
  
  Plot a bar chart to visualize growth/decline in matches.

**4.Top Winning Teams (Univariate Analysis)**

  Use value_counts() on the winner column.
  
  Plot top 5 winning teams in a bar chart.

**5.Toss Decisions (Univariate Analysis)**

  Count toss decision preferences (bat vs field).
  
  Plot results using a bar chart.

**6.Top Venues (Univariate Analysis)**

  Count matches per venue.
  
  Display top 5 venues with a horizontal bar chart.

**7.Draw Insights**

  Observe patterns in toss decisions.
  
  Identify teams with consistent winning trends.
  
## Program and Output
  ```
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
matches = pd.read_csv("matches.csv")
print("Dataset Shape:", matches.shape)   
print(matches.head())                    

```

<img width="1112" height="796" alt="image" src="https://github.com/user-attachments/assets/88df9e54-e4af-4e41-8798-5634f2964e03" />

```

season_counts = matches['season'].value_counts().sort_index()
print("\nMatches per season:\n", season_counts)
plt.figure(figsize=(8,4))
sns.barplot(x=season_counts.index, y=season_counts.values, palette="viridis")
plt.title("Number of Matches per Season")
plt.xlabel("Season")
plt.ylabel("Matches")
plt.show()
```
<img width="1171" height="877" alt="image" src="https://github.com/user-attachments/assets/640b1f1a-ee2a-4c3c-95fa-b1577c7df615" />

```
team_wins = matches['winner'].value_counts()
print("\nTop Winning Teams:\n", team_wins.head(5))
plt.figure(figsize=(8,4))
sns.barplot(x=team_wins.head(5).index, y=team_wins.head(5).values, palette="magma")
plt.title("Top 5 Winning Teams")
plt.xlabel("Team")
plt.ylabel("Wins")
plt.show()

```
<img width="1179" height="720" alt="image" src="https://github.com/user-attachments/assets/c2355444-37a5-4022-8859-690109a48d43" />


```
toss_decision = matches['toss_decision'].value_counts()
print("\nToss Decisions:\n", toss_decision)
plt.figure(figsize=(6,4))
sns.barplot(x=toss_decision.index, y=toss_decision.values, palette="Set2")
plt.title("Toss Decisions (Bat or Field)")
plt.show()
```
<img width="1165" height="631" alt="image" src="https://github.com/user-attachments/assets/74d52ef0-48a7-4af9-9a5d-644b74a971ce" />


```
venue_counts = matches['venue'].value_counts().head(5)
print("\nTop Venues:\n", venue_counts)
plt.figure(figsize=(8,4))
sns.barplot(y=venue_counts.index, x=venue_counts.values, palette="coolwarm")
plt.title("Top 5 Venues by Matches Hosted")
plt.xlabel("Matches Hosted")
plt.ylabel("Venue")
plt.show()
```

<img width="1121" height="704" alt="image" src="https://github.com/user-attachments/assets/d4040328-94c1-47c3-bcfb-2e68a1625fc3" />




 **Result**
 
  This experiment is executed successfully
