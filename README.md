# Election_Analysis

Challenge #3

Election_Analysis

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

The analysis of this election shows that:

There were 369,711 votes casted in this election.
The candidates were:

Charles Casper Stockham
Raymon Anthony Doane
Diana DeGette

The candidate results were:

Charles Casper Stockham received 23.0% of the votes and 85,213 number of votes.
Raymon Anthony Doane received 3.1% of the votes and 11,606 number of votes.
Diana DeGette received 73.8% of the votes and 272,892 number of votes.

The winner of the election was:

Diana DeGette received 73.8% of the votes and 272,892 number of votes.

The counties in the congressional election were:
Arapahoe had 6.7 percent of the votes with 24,801 ballots cast.
Jefferson had 10.5 percent of the votes with 38,855 ballots cast.
Denver had 82.8 percent of the votes with 306,055 ballots cast.

The county with the largest voter turnout was:

Denver


Election Audit Summary

Further analysis could be performed on the existing dataset by modifying the script to count the votes for each candidate by the county the ballot that was cast. Using a conditional statement we can isolate votes for a candidate and the county it came from into a list. This analysis would provide further insight where each candidate's support came from in the overall vote turnout.

For wider use of this code, we could create dictionaries with all the existing counties and congressional district assignments to create a lookup that would allow the script to be utilized for any election in Colorado. Along with additional requirement gathering we could modify the script to process election data, determine the district the ballots are assigned, and run the analysis providing results for any congressional election in Colorado.

Heres my code:
