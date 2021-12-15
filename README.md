# Election_Analysis

Overview of Election Audit

A Colorado Board of Election has requested an election audit of a recent local congressional election.

Calculate the total number of votes cast.
Get a complete list of candidates who received votes.
Calculate the total number of votes each candidate received.
Calculate the percentage of votes each candidate won.
Determine the winner of the election based on popular vote.
Determine the total number of votes and percentages for each county.
Determine the county that had the largest voter turnout.
Resources

– Data Source: election_results.csv – Software: Python 3.6.7, Visual Studio Code, 1.62.3

Election Audit Results

The analysis of the election show that:

There were 369,711 votes cast in the election.


The candidates were:
Charles Casper Stockham
Raymon Anthony Doane
Diana DeGette


The candidate results were:
![Screen Shot 2021-12-12 at 10 50 28 PM](https://user-images.githubusercontent.com/91812090/146120400-cf5ed09a-6ae7-47ea-b7a1-234db18dd0c4.png)

Charles Casper Stockham received 23.0% of the vote and 85,213 number of votes.
Diana DeGette received 73.8% of the vote and 272,892 number of votes.
Raymon Anthony Doane received 3.1% of the vote and 11,606 number of votes.


The winner of the election was:
Diana DeGette received 73.8% of the vote and 272,892 number of votes.
The counties in the congressional election were:

![Screen Shot 2021-12-12 at 10 46 12 PM](https://user-images.githubusercontent.com/91812090/146120352-9c253967-2648-4c48-b45c-239c50615549.png)


Jefferson had 10.5 percent of the votes with 38,855 ballots cast.
Denver had 82.8 percent of the votes with 306,055 ballots cast.
Arapahoe had 6.7 percent of the votes with 24,801 ballots cast.

The county with the largest voter turnout:
Denver





Election Audit Summary

Further analysis could be performed on the existing dataset by modifying the script to count the votes for each candidate by the county the ballot was cast. By using a conditional statement we can isolate votes for a candidate AND the county it came from into a list. This analysis would provide further insight where each candidate's support originated from in the overall vote turnout.

For a wider use of this code, we could create dictionaries with all the existing counties and congressional district assignments to create a lookup that would allow the script to be utilized for any election in Colorado. With additional requirement gathering we could modify the script to injest election data, determine the district the ballots are assigned, and run the analysis providing results for any congressional election in Colorado.
