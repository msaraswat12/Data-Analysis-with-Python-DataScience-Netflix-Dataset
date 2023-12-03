# Data-Analysis-with-Python-DataScience-Netflix-Dataset
It is a project of Data Analysis with Python or you can say, Data Science with Python.

The commands that we used in this project :

* head() - It shows the first N rows in the data (by default, N=5).
* tail () - It shows the last N rows in the data (by default, N=5).
* shape - It shows the total no. of rows and no. of columns of the dataframe.
* size - To show No. of total values(elements) in the dataset.
* columns - To show each Column Name.
* dtypes - To show the data-type of each column.
* info() - To show indexes, columns, data-types of each column, memory at once.
* value_counts - In a column, it shows all the unique values with their count. It can be applied on a single column only.
* unique() - It shows the all unique values of the series.
* nunique() - It shows the total no. of unique values in the series.
* duplicated( ) - To check row wise and detect the Duplicate rows.
* isnull( ) - To show where Null value is present.
* dropna( ) - It drops the rows that contains all missing values.
* isin( ) - To show all records including particular elements.
* str.contains( ) - To get all records that contains a given string.
* str.split( ) - It splits a column's string into different columns.
* to_datetime( ) - Converts the data-type of Date-Time Column into datetime[ns] datatype.
* dt.year.value_counts( ) - It counts the occurrence of all individual years in Time column.
* groupby( ) - Groupby is used to split the data into groups based on some criteria.
* sns.countplot(df['Col_name']) - To show the count of all unique values of any column in the form of bar graph.
* max( ), min( ) - It shows the maximum/minimum value of the series.
* mean( ) - It shows the mean value of the series.

You will learn these things also:
Creating New Columns & Dataframe
Filtering (Single Column & Multiple Columns)
Filtering with And and OR
Seaborn Library - Bar Graphs

.......................................................................

Task. 1) Is there any Duplicate Record in this dataset ? If yes, then remove the duplicate records.
Task. 2) Is there any Null Value present in any column ? Show with Heat-map.
Q. 1)  FOR 'Jailbirds 'New Orleans', What is the show ID and who is the director of the show?
Q. 2) In which year the highest number of the TV Shows & Movies were released ? Show with Bar Graph.
Q. 3) How many Movies & TV Shows are in the dataset ? Show with Bar Graph.
Q. 4) Show all the Movies that were released in year 2000.
Q. 5) Show only the Titles of all TV Shows that were released in India only.
Q. 6) Show Top 10 Directors, who gave the highest number of TV Shows & Movies to Netflix ?
Q. 7) Show all the Records, where "type is Movie and listed_in is Comedies" or "Country is United Kingdom".
Q. 8) In how many movies/shows, Tom Cruise was cast ?
Q. 9) What are the different Ratings defined by Netflix ?
Q. 9.1) How many Movies got the 'TV-14' rating, in Canada ?
Q. 9.2) How many TV Shows got the 'R' rating, after year 2018 ?
Q. 10) What is the maximum duration of a Movie/Show on Netflix ?
Q. 11) Which individual country has the Highest No. of TV Shows ?
Q. 12) How can we sort the dataset by Year ?
Q. 13) Find all the instances where: type is 'Movie' and listed is 'Dramas' or type is 'TV Show' & listed_in is 'Kids' TV'.
