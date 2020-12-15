WORKING TITLE

Idea:

This is a website which allows screenwriters to easily and quickly compare their drafts to produced screenplays in terms of specific content and metrics. This is not meant to replace any story critiques or formatting concerns, but rather to give writers a sense that they are in the ballpark of certain scripts. 

Future development may include developing a Final Draft analysis to focus on specific elements of a screenplay, but the starting format will be pdf.

The website will take in the following information from a user:

-- Screenplay (pdf)
-- Title (text)
-- Genre (text, dropdown selection)
-- Format (text, dropdown selection)

and will report back a metric comparison of the screenplay provided to the full set of screenplays in the repository, or to the screenplays in the genre specified.

the metrics for comparison will be:

-- average sentence length 
	- to be developed into:
			* average action sentence length
			* average length of dialogue
			* max length of monologue


-- average repeated adjective count:
	- to be developed into:
		* number of adjectives included in the top adjectives per genre specified.
		* number of adjectives used from outside the genre specified
		** this will be based on an NLP ML algorithm to learn the main adjectives associated with the genres. 

-- average words per page:
	- to be developed into:
		* TBD
		
-- script rating based on metrics:
	- developing an ML algorithm which classifies the scripts (probably a regression analysis with results between 0 and 10), which tries to rate the provided script as compared to these metrics. Will perform an R-squared analysis of the metrics to understand how closely related the rating is to these metrics initially, then try to narrow down the main metrics that should be used in the score. Try to find a way to quantify:
		- emotional impact
		- visualization
		- story elements
		- plot twists
		- tension building
		- Surprise/shocks
		- etc.
	
	Finding even a cursory metric may help to quantify how the best scripts tackle these things, and may be helpful in developing scripts.
	

Implementation Process:

1) develop an html page hosted locally that can take and store the input data.

2) Create a repository of several top notch scripts, organized by genre and rating (see IMDB for these).

3) Develop a pdf scanning script to evaluate the word count based metrics.

4) Report these metrics back for the scripts in the repository

5) Store these metrics in a sql database

6) attach the metrics to the webpage, so that the results are reported for the screenplay uploaded.

7) Do the average over all scripts for these word count metrics, and compare the range (with standard deviation) to the screenplay provided (threshold goal).
	- Scoring will be: screenplays within an SD of the average are considered good
	- screenplays within 2 SD are considered leary
	- Screenplays outside of 2 SD are not aligned with the top screenplays. 

8) try to do the comparisons by genre only by developing the NLP algorithms.

9) Develop the ML code to develop this regression analysis, and start providing a rating score based on the metrics:
	- start with an average rating score based on the different categories, then try to develop weights.
	

10) Continue to add scripts - monitor the learning algorithms.

11) Host the website and database from an EC2 instance.

14) try to containerize the application.

15) potentially make this service available publicly or primarily to OBS. 




- Films to watch from gathering scripts:
	Romance
	- one good reason (2012)
	- the elixir of love (2009)
	- shoebox memories (2016)
	- the best years (2013)

		





