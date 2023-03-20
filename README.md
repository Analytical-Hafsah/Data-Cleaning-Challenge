# Data-Cleaning-Challenge

Data Cleaning Project with Excel and SQL Server.
•Introduction to Project
The dataset is from Kaggle.com and it consists of 18979 columns and 77 rows.

•This data cleaning was done on both Excel and SQL Server.

To clean list in Excel.

•Name.

•Height

•Value.

•Hits.


To clean list in SQL Server.

•Unwanted Columns.

•Standardize Date Format for Joined column.

•Splitting Contract Column into individual Columns.

•Replacing Clubs with Special Characters.

•Changing Weight Column from kg to lbs.

•Changing Wage column values to thousand.

•Removing the Star character from columns W/F, SM and IR and changing their datatype.


Firstly, I noticed that the name and long name Columns had special characters when I imported the dataset into Excel even though excel power query encoding was set to utf-8 and it also had special characters in SQL Server as well. I decided to clean these columns in Excel because that would get the job done quickly.

DATA CLEANING WITH EXCEL.

•NAME

I used Excel power query to separate the player URL to extract the player’s name. Then I used formula “=SUBSTITUTE (G2,"-"," ")“ to remove the separator sign (–) from the names. And then I used =PROPER(F2) to change the names to Sentence case.

•HEIGHT

The values of the height column were in feet. To change the values from feet to cm, I used Excel power query to remove the “’” and then split the values using a break line which separated the values into separate columns on the sheet. Then I used this formula “=P2*30.48 + Q2*2.54” (30.48 to convert the feet and 2.54 to convert the inches) to covert the two columns to CM.

•VALUE

I used Find and Replace to remove the special character. Then I changed the “M” to “000000” by using this formula “=SUBSTITUTE (T2,"M"," ")*1000000“

•HITS

The Hits Column contain figures like 1.6k. In order to change to correct number format, I used this formular “=LEFT(CC2,FIND(“K”,CC2)-1)*1000”

DATA CLEANING WITH SQL SERVER

•UNWANTED COLUMNS.

While exploring the dataset, I found some unimportant columns that would be irrelevant to future Analysis and Visualization. So, I dropped those Columns.

•STANDARDIZE DATE FORMAT FOR JOINED COLUMN.

The date on the original dataset will interfere with future visualization, I standardized it to correct format.

•SPLITTING CONTRACT COLUMN INTO INDIVIDUAL COLUMNS.

The contract start and end date of each player was joined together which will interfere with visualization, so I Split the Column into individual Columns.

•REPLACING CLUBS WITH SPECIAL CHARACTERS.

Most of the Club names contain special character. It was such a hassle to covert the character to enlist format. It took a while to change these characters because I had to use the UPDATE SET and REPLACE syntaxes a couple of times.

•CHANGING WEIGHT COLUMN FROM KG TO LBS.

I thought changing the Weight Column will be easier and convenient for analysis, so I changed the values to lbs and then convert the data type to integers.

•CHANGING WAGE COLUMN VALUES TO THOUSAND.

For better aggregation and relevant calculations in future analysis, I thought it will be better to change the wage column to thousands. And I also converted the datatype to INT because it was previously in NVARCHAR.

•REMOVING THE STAR CHARACTER FROM COLUMNS.

Columns W/F, SM and IR contain Star special character. I removed them and convert their datatypes to INT 



