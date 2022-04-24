# election-analysis

## Overview of Election Audit: 
During module 3 Tom and Seth requested help analyzing election data, now the commission which they represent is requesting additional information. This additional information is the county specific results and the county analysis. This repository goes over that analysis and the functions we utilized to perform our analysis.

## Election-Audit Results: 
- How many votes were cast in this congressional election?

  The code markup below is the where we are keeping track of how many votes were cast:

  ```python
  for row in reader:
      total_votes = total_votes + 1
  ```
  This for loop allows us to store the vote count data. For each row in the reader.csv it will add 1 to the vote total which starts at 0. In order to not mistakenly count the header line next(header) is utilized when the csv file is initially read and converted into lists of dictionaries. 

  ![totalvotes](https://user-images.githubusercontent.com/101137700/164793264-24c1d2a6-9770-47b5-8422-a541becad8eb.png)

- Provide a breakdown of the number of votes and the percentage of total votes for each county in the precinct.

  With the election result printed there was a very clear winner due to the bulk of the votes ending up in the county of Denver compared to the two other counties in the dataset. 

  First an if statement was created to check the county does not match any in the county list we initialized at the beginning.

  ```python
  if countyName not in counties:
    counties.append(countyName)
    countyVotes[countyName] = 0 #begin tracking the county's vote count
  countyVotes[countyName] += 1 # add a vote to that county's vote count
  ```
  Then to provide the percentage of total votes for each county we take the county votes and divide by total votes and multiply that answer by 100 to get the percentage for each county's results.

  ```python
  vote_percentage = float(cvotes) / float(total_votes) * 100
  county_results = (f"{countyName}: {vote_percentage:.1f}% ({cvotes:,})\n")
  ```
  ![countypercentage](https://user-images.githubusercontent.com/101137700/164793317-f8c97f9e-ff7f-4b50-955c-9ecb5981940b.png)

- Which county had the largest number of votes?

<<<<<<< HEAD
  Using an if statement we determined that Denver was the winning county.

  ```python
  if (cvotes > winning_c_count): 
    winning_c_count = cvotes
    winning_county = countyName
  ```
  ![winningcounty](https://user-images.githubusercontent.com/101137700/164793349-807a4064-382f-43bc-9285-3441e5e0fdd0.png)
=======
  ![winningcounty](https://user-images.githubusercontent.com/101137700/164873229-15394f0c-a6a2-4db4-b6c3-8baba45d089e.png)
>>>>>>> 89bac3ce51fd538c5f53bfa12dcd438e197e13ed

- Provide a breakdown of the number of votes and the percentage of the total votes each candidate received.

  Utilizing a for loop we retrieve the candidate vote count and calculate the percentage for each candidate.

  ```python
  for candidate_name in candidate_votes:
      can_votes = candidate_votes[candidate_name]
      can_vote_percentage = float(can_votes) / float(total_votes) * 100
      candidate_results = (f"{candidate_name}: {can_vote_percentage:.1f}% ({can_votes:,})\n")
  ```
  ![candidatepercentage](https://user-images.githubusercontent.com/101137700/164793365-114724ac-0a0c-4249-a5de-6fa51e19f354.png)

- Which candidate won the election, what was their vote count, and what was their percentage of the total votes?

Just like in the case of the county results there was a clear winner in the candidates results. This was found using an if statement that compared the candidate votes to the winning count and the candidate vote percentage to the candidate winning percentage. When it finds those variables it assigns them to those winning variables to then produce the summary in the image below.

```python
  if (can_votes > winning_count) and (can_vote_percentage > can_winning_percentage):
      winning_count = can_votes
      winning_candidate = candidate_name
      winning_percentage = can_vote_percentage
```
  ![winningcandidate](https://user-images.githubusercontent.com/101137700/164793384-30b05c1c-d643-4692-99fd-1e6e98851075.png)

## Election-Audit Summary: In a summary statement, provide a business proposal to the election commission on how this script can be used—with some modifications—for any election. 
- Give at least two examples of how this script can be modified to be used for other elections.

  This script can easily be modified using similar datasets. One of those ways is that you could import districts and break the counties into districts to understand more specific candidate impact. This narrows the scope of the script into more niche locations for specific needs of candidates. 

  The second way that this script can be modified is that it can possibly be turned into a function where you can apply it to multiple locations and then compare those results. This broadens the scope of the script and allows you to widen the analysis.