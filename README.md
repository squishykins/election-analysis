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

  ![countypercentage](https://user-images.githubusercontent.com/101137700/164793317-f8c97f9e-ff7f-4b50-955c-9ecb5981940b.png)

- Which county had the largest number of votes?

  ![winningcounty](https://user-images.githubusercontent.com/101137700/164873229-15394f0c-a6a2-4db4-b6c3-8baba45d089e.png)

- Provide a breakdown of the number of votes and the percentage of the total votes each candidate received.

  ![candidatepercentage](https://user-images.githubusercontent.com/101137700/164793365-114724ac-0a0c-4249-a5de-6fa51e19f354.png)

- Which candidate won the election, what was their vote count, and what was their percentage of the total votes?

  ![winningcandidate](https://user-images.githubusercontent.com/101137700/164793384-30b05c1c-d643-4692-99fd-1e6e98851075.png)

## Election-Audit Summary: In a summary statement, provide a business proposal to the election commission on how this script can be used—with some modifications—for any election. 
- Give at least two examples of how this script can be modified to be used for other elections.
