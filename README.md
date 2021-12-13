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

![Screen Shot 2021-12-12 at 10 42 27 PM](https://user-images.githubusercontent.com/91812090/145753687-cd7569de-5779-435b-8d64-9326fa05cdec.png)

There were 369,711 votes casted in this election.
The candidates were:

Charles Casper Stockham
Raymon Anthony Doane
Diana DeGette

The candidate results were:
![Screen Shot 2021-12-12 at 10 46 50 PM](https://user-images.githubusercontent.com/91812090/145754016-412c4cb4-e37a-471f-87ed-034f4a0ee3e0.png)

Charles Casper Stockham received 23.0% of the votes and 85,213 number of votes.
Raymon Anthony Doane received 3.1% of the votes and 11,606 number of votes.
Diana DeGette received 73.8% of the votes and 272,892 number of votes.

The winner of the election was:

Diana DeGette received 73.8% of the votes and 272,892 number of votes.
![Screen Shot 2021-12-12 at 10 52 23 PM](https://user-images.githubusercontent.com/91812090/145754432-ea391c3e-2396-43c3-beb3-5dcf8c7db722.png)


The counties in the congressional election were:
Arapahoe had 6.7 percent of the votes with 24,801 ballots cast.
Jefferson had 10.5 percent of the votes with 38,855 ballots cast.
Denver had 82.8 percent of the votes with 306,055 ballots cast.

![Screen Shot 2021-12-12 at 10 50 28 PM](https://user-images.githubusercontent.com/91812090/145754292-2775f93a-5e46-463e-9090-b8b209e57c2a.png)

The county with the largest voter turnout was:

Denver

![Screen Shot 2021-12-12 at 10 49 16 PM](https://user-images.githubusercontent.com/91812090/145754190-cd75f833-0fc8-4dcd-9e4d-9e8aab0f98be.png)


Election Audit Summary

Further analysis could be performed on the existing dataset by modifying the script to count the votes for each candidate by the county the ballot that was cast. Using a conditional statement we can isolate votes for a candidate and the county it came from into a list. This analysis would provide further insight where each candidate's support came from in the overall vote turnout.

For wider use of this code, we could create dictionaries with all the existing counties and congressional district assignments to create a lookup that would allow the script to be utilized for any election in Colorado. Along with additional requirement gathering we could modify the script to process election data, determine the district the ballots are assigned, and run the analysis providing results for any congressional election in Colorado.

Heres my code:
# -*- coding: UTF-8 -*-
"""PyPoll Homework Challenge Solution."""

# Add our dependencies.
import csv
import os

# Add a variable to load a file from a path.
file_to_load = os.path.join("Resources", "election_results.csv")
# Add a variable to save the file to a path.
file_to_save = os.path.join("analysis", "election_analysis.txt")

# Initialize a total vote counter.
total_votes = 0

# Candidate Options and candidate votes.
candidate_options = []
candidate_votes = {}

# 1: Create a county list and county votes dictionary.
county_options=[]
county_votes={}

# Track the winning candidate, vote count and percentage
winning_candidate = ""
winning_count = 0
winning_percentage = 0

# 2: Track the largest county and county voter turnout.
winning_county=""
winning_county_count=0
winning_county_percentage=0

# Read the csv and convert it into a list of dictionaries
with open(file_to_load) as election_data:
    reader = csv.reader(election_data)

    # Read the header
    header = next(reader)

    # For each row in the CSV file.
    for row in reader:

        # Add to the total vote count
        total_votes = total_votes + 1

        # Get the candidate name from each row.
        candidate_name = row[2]

        # 3: Extract the county name from each row.
        county_name=row[1]

        # If the candidate does not match any existing candidate add it to
        # the candidate list
        if candidate_name not in candidate_options:

            # Add the candidate name to the candidate list.
            candidate_options.append(candidate_name)

            # And begin tracking that candidate's voter count.
            candidate_votes[candidate_name] = 0

        # Add a vote to that candidate's count
        candidate_votes[candidate_name] += 1

        # 4a: Write an if statement that checks that the
        # county does not match any existing county in the county list.
        if county_name not in county_options:

            # 4b: Add the existing county to the list of counties.
            county_options.append(county_name)

            # 4c: Begin tracking the county's vote count.
            county_votes[county_name]=0

        # 5: Add a vote to that county's vote count.
        county_votes[county_name]+=1


# Save the results to our text file.
with open(file_to_save, "w") as txt_file:

    # Print the final vote count (to terminal)
    election_results = (
        f"\nElection Results\n"
        f"-------------------------\n"
        f"Total Votes: {total_votes:,}\n"
        f"-------------------------\n\n"
        f"County Votes:\n")
    print(election_results, end="")

    txt_file.write(election_results)

    # 6a: Write a for loop to get the county from the county dictionary.
    for county_name in county_votes:
        # 6b: Retrieve the county vote count.
        votes=county_votes[county_name]
        # 6c: Calculate the percentage of votes for the county.
        vote_percentage=float(votes)/float(total_votes)*100

         # 6d: Print the county results to the terminal.
        county_results=( f"{county_name}:{vote_percentage:.1f}% ({votes:,})\n")
        print(county_results)
         # 6e: Save the county votes to a text file.
        txt_file.write(county_results)
         # 6f: Write an if statement to determine the winning county and get its vote count.
        if (votes>winning_county_count) and (vote_percentage>winning_county_percentage):

            winning_county_count=votes
            winning_county=county_name
            winning_county_percentage=vote_percentage

    # 7: Print the county with the largest turnout to the terminal.
    largest_county_turnout=(
        f"-------------------\n"
        f"Largest County Turnout: {winning_county}\n"
        f"-------------------\n"
    )
    print(largest_county_turnout)
    # 8: Save the county with the largest turnout to a text file.
    txt_file.write(largest_county_turnout)

    # Save the final candidate vote count to the text file.
    for candidate_name in candidate_votes:

        # Retrieve vote count and percentage
        votes = candidate_votes.get(candidate_name)
        vote_percentage = float(votes) / float(total_votes) * 100
        candidate_results = (
            f"{candidate_name}: {vote_percentage:.1f}% ({votes:,})\n")

        # Print each candidate's voter count and percentage to the
        # terminal.
        print(candidate_results)
        #  Save the candidate results to our text file.
        txt_file.write(candidate_results)

        # Determine winning vote count, winning percentage, and candidate.
        if (votes > winning_count) and (vote_percentage > winning_percentage):
            winning_count = votes
            winning_candidate = candidate_name
            winning_percentage = vote_percentage

    # Print the winning candidate (to terminal)
    winning_candidate_summary = (
        f"-------------------------\n"
        f"Winner: {winning_candidate}\n"
        f"Winning Vote Count: {winning_count:,}\n"
        f"Winning Percentage: {winning_percentage:.1f}%\n"
        f"-------------------------\n")
    print(winning_candidate_summary)

    # Save the winning candidate's name to the text file
    txt_file.write(winning_candidate_summary)
