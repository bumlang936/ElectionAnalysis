# Election Analysis

## Project Overview
A Colorado Board of Elections employee, "Seth", has given the following tasks to complete an election audit within a local congressional election.

1. Calculate the total number of votes cast.
2. Get a complete list of candidates who received votes.
3. Calculate the total number of votes each candidate received.
4. Calculate the percentage of votes each candidate won.
5. Determine the winner of the election based on popular vote. 

## Resources
- Data Source: election_results.csv
- Software: Python 3.7.6, Visual Studio Code, 1.52.1

## Project Results
The analysis of the election show that:
- There were 369,711 votes cast in the election.
- The candidates were:
  - Charles Casper Stockham
  - Diana DeGette
  - Raymon Anthony Doane
- The candidate results were:
  - Charles Casper Stockham received 23.0% of the vote and 85,213 number of votes.
  - Diana DeGette received 73.8% of the vote and 272,892 number of votes.
  - Raymon Anthony Doane received 3.1% of the vote and 11,606 number of votes.
- The winner of the election was:
  - Diana DeGette with 85,213 votes and 73.8% of the total vote.

## Challenge Overview
A Colorado Board of Elections employee, "Seth", has given the following tasks to complete the election audit within a local congressional election.

1. Calculate the total number of votes cast.
2. Get a complete list of candidates who received votes.
3. Calculate the total number of votes each candidate received.
4. Calculate the percentage of votes each candidate won.
5. Determine the winner of the election based on popular vote. 

Now the election committee has requested some additional data to complete the audit.

1. The voter turnout for each county.
2. The percentage of votes from each county out of the total count.
3. The county with the highest turnout.

## Resources
- Data Source: election_results.csv
- Software: Python 3.7.6, Visual Studio Code, 1.52.1

## Challenge Results
The analysis of the election show that:
- There were 369,711 votes cast in the election.
- The counties were:
  - Jefferson
  - Denver
  - Arapahoe
- The county results were:
  - Jefferson County had a total of 38,855 votes, which was 10.5% of the total vote.
  - Denver County had a total of 306,055 votes, which was 82.8% of the total vote.
  - Arapahoe County had a total of 24,801 votes, which was 6.7% of the total vote.
- The county with the highest voter turnout was:
  - Denver County with 306,055 votes, which was 82.8% of the total vote.
- The candidates were:
  - Charles Casper Stockham
  - Diana DeGette
  - Raymon Anthony Doane
- The candidate results were: 
  - Charles Casper Stockham received 23.0% of the vote and 85,213 number of votes.
  - Diana DeGette received 73.8% of the vote and 272,892 number of votes.
  - Raymon Anthony Doane received 3.1% of the vote and 11,606 number of votes.
- The winner of the election was:
  - Diana DeGette with 85,213 votes and 73.8% of the total vote.

## Election-Audit Summary
If the election commission wanted to use this code for future elections, they would be able to use this code to find out other kinds of data by giving this code a slight modification. There are "for" loops created that iterate through each row of the provided election_results.csv, looking for a specific variable and then increments that variable by 1 every time it is found. If there was an election that provided the voters ethnicity, then the code would only need to be slightly modified to find the percentage for each ethnic group that voted in the election. If the election_results.csv provided the ethnicity of each voter in the D column, then only two new variables need to be made along with adjusting the "for" loops in the code. This could easily be done by copying the two variables that created a list and dictionary for the candidate and county values. So the new variables that would be added would be:

ethnicity_options = []

ethnicity_votes = {} 

Then the variables names would need to be changed in the "for" loop that reads through the election_results.csv to match the newly created variables. The "for" loop would now be: 

for row in reader:
  ---total_votes = total_votes + 1
  ---ethnicity_name = row[3]
  ---if ethnicity_name not in ethnicity_options:
    ethnicity_options.append(ethnicity_name)
    ethnicity_votes[ethnicity_name] = 0
    ethnicity_votes[ethnicity_name] += 1
    
Another quick change would be to the "for" loop that helps calculate the percentage and then writes that data to the election_results.txt file. The "for" loop would now look like:

for ethnicity_name in ethnicity_votes:
  ethnicity_vote = ethnicity_votes[ethnicity_name]
  ethnicity_vote_percentage = float(ethnicity_vote)/float(total_votes) * 100
  ethnicity_results = (
  f"{ethnicity_name}: {ethnicity_vote_percentage:.1f}% ({ethnicity_vote:,})\n")
  print(ethnicity_results)
  txt_file.write(ethnicity_results)
 
Basically the only modification that was made, was that the variable names were changed to match the data that was being analyzed. The code was written in a way that would make it easy to find totals and percentages for any data that could be valuable. So if the election_results.csv had another column that listed the voter's party affiliation, the same code could be used to find out what percentage of each party affiliation voted for a certain candidate. The only modifications needed to be made would be to create new variables that create a list and dictionary for the party affiliation values, along with changing the variables in the "for" loops so that they match the new variables that were created. So for future elections, this code can be used to help find totals and percentages of important data like ethnicity, party affiliation, age group, gender, etc. and can also be used to find the totals and percentages of that data that voted for each candidate. 
        
        
 
