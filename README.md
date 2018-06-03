# Acadgild-Dataanalytics-session2-assignment2
DATA ANALYTICS WITH R, EXCEL AND TABLEAU SESSION 2 ASSIGNMENT 2
Solution to assignment2 is uploaded as attachment separately
Problem	Solutions
1. Read multiple JSON files into a directory to convert into a dataset.
I have files text1, text2, text3 in the directory JSON.	Read the JSON File
The JSON file is read by R using the function from JSON(). It is stored as a list in R.
# Load the package required to read JSON files.
library("rjson")

# Give the input file name to the function.
result <- fromJSON(file = "input.json")

# Print the result.
print(result)
When we execute the above code, it produces the following result −
$ID
[1] "1"   "2"   "3"   "4"   "5"   "6"   "7"   "8"

$Name
[1] "Rick"     "Dan"      "Michelle" "Ryan"     "Gary"     "Nina"     "Simon"    "Guru"

$Salary
[1] "623.3"  "515.2"  "611"    "729"    "843.25" "578"    "632.8"  "722.5"

$StartDate
[1] "1/1/2012"   "9/23/2013"  "11/15/2014" "5/11/2014"  "3/27/2015"  "5/21/2013"
   "7/30/2013"  "6/17/2014"

$Dept
[1] "IT"         "Operations" "IT"         "HR"         "Finance"    "IT"
   "Operations" "Finance"
Convert JSON to a Data Frame
We can convert the extracted data above to a R data frame for further analysis using the as.data.frame() function.
# Load the package required to read JSON files.
library("rjson")

# Give the input file name to the function.
result <- fromJSON(file = "input.json")

# Convert JSON file to a data frame.
json_data_frame <- as.data.frame(result)

print(json_data_frame)
When we execute the above code, it produces the following result −
      id,   name,    salary,   start_date,     dept
1      1    Rick     623.30    2012-01-01      IT
2      2    Dan      515.20    2013-09-23      Operations
3      3    Michelle 611.00    2014-11-15      IT
4      4    Ryan     729.00    2014-05-11      HR
5     NA    Gary     843.25    2015-03-27      Finance
6      6    Nina     578.00    2013-05-21      IT
7      7    Simon    632.80    2013-07-30      Operations
8      8    Guru     722.50    2014-06-17      Finance
 
2. Parse the following JSON into a data frame.
js<-'{
"name": null, "release_date_local": null, "title": "3 (2011)",
"opening_weekend_take": 1234, "year": 2011,
"release_date_wide": "2011-09-16", "gross": 59954
}	 
3. Write a script for Variable Binning using R.	 
