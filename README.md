# Overview of Election Audit
The purpose of the election audit and analysis is to count all submitted votes and determine the winning official.  In addition to presenting the winner, the following data was collected and presented to the commission:

- The voter turnout for each county
- The percentage of votes from each county out of the total count
- The county wiht the highest turnout

# Election-Audit Results

![Results](Resources/analysis-terminal.png)

- ### How many votes were cast in this congressional election?

    369,711 total votes were cast in the congressional election

    ###### each row in the file represented a vote
    
    ```python
    total_votes = 0

    with open(file_to_load) as election_data:
        reader = csv.reader(election_data)

        for row in reader:

            total_votes = total_votes + 1
    ```

- ### Provide a breakdown of the number of votes and the percentage of total votes for each county in the precinct.

    - Jefferson county made up 10.5% of total votes with 85,213
    - Denver county made up 82.8% of total votes with 306,055
    - Arapahoe county made up 6.7% of total votes with 24,801  
  

    ###### store each county:count in a dictionary

    ```python
    for row in reader:
        
        if county_name not in counties:

            counties.append(county_name)

            counties_votes[county_name] = 0

        counties_votes[county_name] += 1    
    ```

- ### Which county had the largest number of votes?

    Denver county had the largest number of votes  

    ###### iterate each dictionary entry and compare votes to determine the largest total
    ```python
    for county_name in counties_votes:

        votes = counties_votes[county_name]

        if (votes > largest_county_votes):
            largest_county_votes = votes
            largest_county = county_name
    ```

- ### Provide a breakdown of the number of votes and the percentage of the total votes each candidate received.

    - Charles Casper Stockham received 23% of the votes with 85,213
    - Diana DeGette received 73.8% of the votes with 272,892
    - Raymon Anthony Doane received 3.1% of the votes with 11,606  

    ###### iterate each candidate in dictionary to calculatae percentage and compare total votes to determine winner
    ```python
    for candidate_name in candidate_votes:

        votes = candidate_votes.get(candidate_name)
        vote_percentage = float(votes) / float(total_votes) * 100

        if (votes > winning_count) and (vote_percentage > winning_percentage):
            winning_count = votes
            winning_candidate = candidate_name
            winning_percentage = vote_percentage
    ```

- ### Which candidate won the election, what was their vote count, and what was their percentage of the total votes?

    Diana DeGette won the election with 272,892 votes which made up 73.8% of the total votes submitted


# Election-Audit Summary

## Business Proposal
This script can be used to calculate the results of state elections and scale to variable number of candidates with variable number of counties.

### Modification #1
Adding a state column to the import file and adjusting the code to calculate state totals per candidate would allow this script to be used for the presidential popular vote.  Additional analysis could be done to identify favorites in different areas of the country.

### Modification #2
Changing the county column to a generic category column would expand the types of elections the script could be used.  For example, the category column could contain school districts and calculate the winner of a superintendent election.