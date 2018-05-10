# canvas_grade_reports
pull_curr_grades.rb uses the Canvas APIs to generate a csv report for all jumpstart students.
The field pulled is the current_score field, and presumes grading periods are not being used.
To run, the script requires a csv file titled user_ids which contains 2 fields: User and Canvas_Id
If the Canvas Ids are not known, the get_canvas_ids.rb script can be used to the user_ids.csv from a file
containing the student's name and SIS_Id 

Instructions
1. If not already installed, install the following Ruby gems:
	json
	csv
	typhoeus
	
2. If Canvas Ids are needed, you'll need to run the get_canvas_ids.rb script
	a. This script takes a csv file which must have the column headers: User and SIS_Id	
	b. The csv file should be called: user_sis.ids.csv and should be saved in the same directory as the script
	c. In a text editor, update lines 13 and 14 to your instance's URL and your token. I recommend using beta or test 
	environments first.
	d. If the csv input file is not in the same folder as the script, update line 16 to the full location of the file
	
	Run the Ruby script. This will create the user_id file, which will be used to pull grades.
	If there are no enrollment changes, the user_id file should only need to be generated once time.
	
3. To run the student grades,
	Edit the pull_curr_grades.rb script:
		update lines 9 and 10 to your instance's URL and your token
		
	Run the script. This will generate a file called: "jumpstart_grades_{today's date}.csv" in the same
	directory as the script. The file will contain the student's name, grade (if less than 70%) and course name
	
	
