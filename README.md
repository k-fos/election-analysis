# Overview of Election Audit
The purpose of the election audit and analysis is to count all submitted votes and determine the winning official.  In addition to presenting the winner, the following data was collected and presented to the commission:

- The voter turnout for each county
- The percentage of votes from each county out of the total count
- The county wiht the highest turnout

# Election-Audit Results

- ### How many votes were cast in this congressional election?

    369,711 total votes were cast in the congressional election

    ##### each row in the file represented a vote
    ```python
    total_votes = 0

    # omitted lines of code

    # Read the csv and convert it into a list of dictionaries
    with open(file_to_load) as election_data:
        reader = csv.reader(election_data)

        # omitted lines

        for row in reader:

            total_votes = total_votes + 1
    ```

- ### Provide a breakdown of the number of votes and the percentage of total votes for each county in the precinct.

- ### Which county had the largest number of votes?

- ### Provide a breakdown of the number of votes and the percetnage of the total votes each candidate received.

- ### Which candidate won the election, what was their vote count, and what was their percentage of the total votes?


# Election-Audit Summary

## Business Proposal

### Modification #1

### Modification #2