# Data Analysis Project: Exploring Netflix Dataset 🎬📊
Introduction:
In this project, I delved into a comprehensive analysis of a Netflix dataset using Python's powerful data manipulation and visualization libraries. The objective was to gain insights into the content available on Netflix and answer various intriguing questions.
Dataset Exploration:
To kick off our exploration, I utilized common DataFrame commands to understand the structure and content of the dataset.

The commands that we used in this project :

# Import necessary libraries
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

# Load the dataset
df = pd.read_csv("your_dataset.csv")

# head() - It shows the first N rows in the data (by default, N=5).
df_head = df.head()

# tail() - It shows the last N rows in the data (by default, N=5).
df_tail = df.tail()

# shape - It shows the total no. of rows and no. of columns of the dataframe.
df_shape = df.shape

# size - To show No. of total values(elements) in the dataset.
df_size = df.size

# columns - To show each Column Name.
df_columns = df.columns

# dtypes - To show the data-type of each column.
df_dtypes = df.dtypes

# info() - To show indexes, columns, data-types of each column, memory at once.
df_info = df.info()

# value_counts - In a column, it shows all the unique values with their count.
# It can be applied on a single column only.
value_counts_col = df['Col_name'].value_counts()

# unique() - It shows the all unique values of the series.
unique_col = df['Col_name'].unique()

# nunique() - It shows the total no. of unique values in the series.
nunique_col = df['Col_name'].nunique()

# duplicated( ) - To check row wise and detect the Duplicate rows.
duplicated_rows = df[df.duplicated()]

# isnull( ) - To show where Null value is present.
is_null = df.isnull()

# dropna( ) - It drops the rows that contain all missing values.
df_dropna = df.dropna()

# isin( ) - To show all records including particular elements.
isin_records = df[df['Col_name'].isin(['value1', 'value2'])]

# str.contains( ) - To get all records that contain a given string.
contains_string_records = df[df['Col_name'].str.contains('substring')]

# str.split( ) - It splits a column's string into different columns.
df_split = df['Col_name'].str.split(expand=True)

# to_datetime( ) - Converts the data-type of Date-Time Column into datetime[ns] datatype.
df['date_column'] = pd.to_datetime(df['date_column'])

# dt.year.value_counts( ) - It counts the occurrence of all individual years in the Time column.
year_counts = df['date_column'].dt.year.value_counts()

# groupby( ) - Groupby is used to split the data into groups based on some criteria.
grouped_df = df.groupby('Col_name')

# sns.countplot(df['Col_name']) - To show the count of all unique values of any column in the form of a bar graph.
plt.figure(figsize=(10, 6))
sns.countplot(x=df['Col_name'])
plt.show()

# max( ), min( ) - It shows the maximum/minimum value of the series.
max_value = df['Col_name'].max()
min_value = df['Col_name'].min()

# mean( ) - It shows the mean value of the series.
mean_value = df['Col_name'].mean()



.......................................................................
# Import necessary libraries
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

# Load the dataset
df = pd.read_csv("your_dataset.csv")

# Task 1: Remove Duplicate Records
df.drop_duplicates(inplace=True)

# Task 2: Check for Null Values and Display with Heatmap
plt.figure(figsize=(10, 6))
sns.heatmap(df.isnull(), cmap='viridis', cbar=False)
plt.show()

# Q. 1: 'Jailbirds New Orleans' Show Information
jailbirds_info = df[df['title'] == "Jailbirds New Orleans"][['show_id', 'director']]
print("Show ID and Director for 'Jailbirds New Orleans':")
print(jailbirds_info)

# Q. 2: Bar Graph for the Year with the Highest Number of Releases
plt.figure(figsize=(10, 6))
sns.countplot(x=df['release_year'], palette='viridis', order=df['release_year'].value_counts().index)
plt.title("Number of TV Shows and Movies Released Each Year")
plt.xlabel("Release Year")
plt.ylabel("Count")
plt.show()

# Q. 3: Bar Graph for the Number of Movies and TV Shows
plt.figure(figsize=(8, 5))
sns.countplot(x='type', data=df, palette='viridis')
plt.title("Number of Movies and TV Shows on Netflix")
plt.xlabel("Type")
plt.ylabel("Count")
plt.show()

# Q. 4: Show all the Movies that were released in the year 2000
movies_2000 = df[(df['type'] == 'Movie') & (df['release_year'] == 2000)][['title', 'release_year']]
print("Movies Released in 2000:")
print(movies_2000)

# Q. 5: Show only the Titles of all TV Shows that were released in India only
indian_tv_shows = df[(df['type'] == 'TV Show') & (df['country'] == 'India')]['title']
print("TV Shows Released in India:")
print(indian_tv_shows)

# Q. 6: Show Top 10 Directors, who gave the highest number of TV Shows & Movies to Netflix
top_directors = df['director'].value_counts().head(10)
print("Top 10 Directors on Netflix:")
print(top_directors)

# Q. 7: Show all the Records, where "type is Movie and listed_in is Comedies" or "Country is United Kingdom"
filtered_records = df[((df['type'] == 'Movie') & (df['listed_in'].str.contains('Comedies'))) |
                      (df['country'] == 'United Kingdom')]
print("Records where type is Movie and listed_in is Comedies or country is United Kingdom:")
print(filtered_records)

# Q. 8: In how many movies/shows, Tom Cruise was cast?
tom_cruise_count = df[df['cast'].str.contains('Tom Cruise', na=False)].shape[0]
print(f"Number of Movies/Shows with Tom Cruise: {tom_cruise_count}")

# Q. 9: What are the different Ratings defined by Netflix?
ratings_list = df['rating'].unique()
print("Different Ratings on Netflix:")
print(ratings_list)

# Q. 9.1: How many Movies got the 'TV-14' rating, in Canada?
tv_14_count_canada = df[(df['rating'] == 'TV-14') & (df['country'] == 'Canada')].shape[0]
print(f"Number of Movies with 'TV-14' rating in Canada: {tv_14_count_canada}")

# Q. 9.2: How many TV Shows got the 'R' rating, after year 2018?
r_rating_tv_shows = df[(df['type'] == 'TV Show') & (df['rating'] == 'R') & (df['release_year'] > 2018)].shape[0]
print(f"Number of TV Shows with 'R' rating after 2018: {r_rating_tv_shows}")

# Q. 10: What is the maximum duration of a Movie/Show on Netflix?
max_duration = df['duration'].str.extract('(\d+)').astype(float).max()
print(f"Maximum Duration of a Movie/Show on Netflix: {max_duration} minutes")

# Q. 11: Which individual country has the Highest No. of TV Shows?
top_country_tv_shows = df[df['type'] == 'TV Show']['country'].value_counts().idxmax()
print(f"Country with the Highest Number of TV Shows: {top_country_tv_shows}")

# Q. 12: How can we sort the dataset by Year?
sorted_df = df.sort_values(by='release_year')
print("Dataset Sorted by Year:")
print(sorted_df)

# Q. 13: Find all the instances where: type is 'Movie' and listed is 'Dramas' or type is 'TV Show' & listed_in is 'Kids' TV
filtered_instances = df[((df['type'] == 'Movie') & (df['listed_in'].str.contains('Dramas'))) |
                        ((df['type'] == 'TV Show') & (df['listed_in'].str.contains("Kids' TV")))]
print("Instances where type is 'Movie' and listed is 'Dramas' or type is 'TV Show' & listed_in is 'Kids' TV:")
print(filtered_instances)

Conclusion:
This project showcases the power of Python for data analysis and visualization, providing a comprehensive exploration of a Netflix dataset. By employing various commands and libraries, we answered diverse questions and gained valuable insights into the content available on the popular streaming platform. Feel free to explore the code, adapt it to your needs, and let the data tell its fascinating story!
