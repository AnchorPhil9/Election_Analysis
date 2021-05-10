# Polling with Python
Starting off with a CSV file containing information of voting for three candidates in three counties, we will be augmenting existing Python code to quickly determine the county with the largest overall voter turnout. 

## Basis
Finding the largest of the three counties by voter turnout will require familiarity with Python. Fortunately, we have starter code ready to be executed and ultimately tell us the winning candidate of this scenario election (“Module 3 Challenge”, 2021), which we can use to base off our new code. It helps, too, that the starter code contains numbered comments that point to where we should add our lines of code (“Module 3 Challenge”, 2021). Of course, since we’d like to know more about county voting data as opposed to candidate data, we will need to make sure our new code focuses on the counties.

## Part 1
Just like with candidate starter code, we will need to identify some initial priorities. We want to get the counties involved with the election using Python, which we can do using a for loop and then adding those counties’ names to a list (3.5.2, 2021). After declaring our county list as simply “county_list” and following the pattern for making our for loop, we subsequently specify the location of our county names as county_name = row[1], since the second column is indexed as column #1 just as the third is indexed as column #2 (3.5.2, 2021). Next, we made sure to have an append() function append county names to our list of counties, per the corresponding candidate code (3.5.2, 2021). Lastly, to make sure we don’t get duplicate entries in county_name, we have added an **if** statement with the **not in** operator, following the starter code’s example for unique candidate names (3.5.2. 2021).

## Part 2
Now that we have our county names addressed, we can get started with counting the votes of each county. Just as the starter code paired up candidates with their respective total votes, we will pair up each county with its respective total votes with the help of a dictionary (“3.5.3”, 2021). Following the starter code’s example, we create a new dictionary for our county votes – called county_votes – and added keys to our dictionary using the entries from county_name (“3.5.3”, 2021). To get the sum data for our county votes, we initialize an accumulator variable **county_votes[county_name]**, setting it equal to zero and then incrementing it with the **+= 1** syntax (“3.5.3”, 2021). Moreover, we aligned the incrementing code with the **if…not in** statement we made beforehand so that each county’s vote gets counted (“3.5.3”, 2021). With these preparations complete, we can set up a for loop to retrieve vote counts for each county, assigning a new variable **cvotes** to equal **county_votes[county_name]** (“3.5.4”, 2021). Afterwards, we calculate the percentage of votes, making sure to first convert our **cvotes** and **total_votes** values into floating decimal numbers (“3.5.4”, 2021). With our vote data calculated, we can print out the results using f-strings (“3.2.11”, 2021), and to write them into our txt file, we assign the f-string printed results a variable **county_results**, which we will write into our txt file (“3.6.1”, 2021). We then added the **end=""** syntax to our print statement to guarantee that any subsequent code that we want printed will get printed on a new line (“3.6.1”, 2021). Furthermore, we added the newline escape sequence **\n** to our county_results to make sure each county result has its own line (“3.6.2”, 2021).

## Part 3
While one could look at the results data and easily find the county has the largest turnout, we can go the next step and have Python determine the largest county by turnout and write that into our txt file. Just like with the candidates data, we need to declare some new variables and place them before the **with open()** statement (“3.5.5”, 2021). In our case, one of these variables has an empty string reserved for the largest county while the other, initially equal to 0, will represent the total turnout for the largest county (“3.5.5”, 2021). Next, we use an if statement within the for loop code, allowing Python to check which one of the county’s **cvotes** values is the largest and fill the empty string variable with the name of our largest county (“3.5.5”, 2021). Based on this setup (“3.5.5”, 2021), we can infer that during the first iteration of the for loop, since the total votes for each county all exceed 0, the largest_turnout will be whichever county’s **cvotes** is checked first. In the following iterations, Python will check to see if the **largest_turnout** value exceeds the next *cvotes* values, adjusting largest_turnout if needed in each iteration such that we end up with the truly largest turnout among our counties. To see what Python has found the county we are looking for, we print out the results with an f-string variable **largest_county_summary** just as in Part 2 (“3.2.11”, 2021; “3.6.1”, 2021). Additionally, we add a newline escape sequence that gives our printed text one line of separation between it and the printed text from Part 2 (“3.4.3”, 2021). Last but not least, we save the largest county results to our file (“3.6.1”, 2021).

## Results, Challenges, and Conclusion
With our additions to the starter code, we ultimately find that Denver county had the largest turnout among the three counties in this election case. In accordance with the expected results for this Challenge (“Module 3 Challenge”, 2021), our written results show that Denver boasted a turnout of 306,055, easily beating the next largest turnout of 38,855 from Jefferson county. 

## Works Cited

3.2.11 Printing Formats (2021). Bootcamp Spot. Retrieved May 8, 2021 from https://
	courses.bootcampspot.com/courses/577/pages/3-dot-2-11-printing-formats

3.4.3 Write to Files with Python (2021). Bootcamp Spot. Retrieved May 8, 2021, from https://
	courses.bootcampspot.com/courses/577/pages/3-dot-4-3-write-to-files-with-python

3.5.2 Get the Candidates in the Election (2021). Bootcamp Spot. Retrieved May 8, 2021, from https://
	courses.bootcampspot.com/courses/577/pages/3-dot-5-2-get-the-candidates-in-the-election

3.5.3 Get the Candidates’ Votes (2021). Bootcamp Spot. Retrieved May 8, 2021, from https://
	courses.bootcampspot.com/courses/577/pages/3-dot-5-3-get-the-candidates-votes

3.5.4 Determine Candidates’ Percentage of Votes (2021). Bootcamp Spot. Retrieved May 8, 2021 from https://
	courses.bootcampspot.com/courses/577/pages/3-dot-5-4-determine-candidates-percentage-of-votes

3.5.5 Determine the Winning Candidate (2021). Bootcamp Spot. Retrieved May 8, 2021 from https://
	courses.bootcampspot.com/courses/577/pages/3-dot-5-5-determine-the-winning-candidate

3.6.1 Write the Election Results to a Text File (2021). Bootcamp Spot. Retrieved May 8, 2021 from https://
	courses.bootcampspot.com/courses/577/pages/3-dot-6-1-write-the-election-results-to-a-text-file

3.6.2 Write the Candidates’ Results to a Text File (2021). Bootcamp Spot. Retrieved May 8, 2021 from https://
	courses.bootcampspot.com/courses/577/pages/3-dot-6-2-write-the-candidates-results-to-a-text-file

Module 3 Challenge (2021). Bootcamp Spot. Retrieved May 9, 2021, from https://
	courses.bootcampspot.com/courses/577/assignments/11853



