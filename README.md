# Netflix Dashboard


This Power BI dashboard provides an interactive analysis of Netflix's content library, focusing on movies and their distribution across various dimensions. It presents insights into the total number of shows, dominant content types, release trends, country-wise content distribution, show duration, director statistics, and content ratings.

* Key Highlights:

Total movies and unique directors on the platform

Country-wise breakdown of Netflix content

Show distribution by type, release year, and rating

Analysis of longest-running shows

Interactive filters by country, release year, and show type


Designed with a sleek dark theme, the dashboard offers a user-friendly interface for exploring trends and making data-driven content decisions.


---

# Steps 

- Step 1: Data Collection and Import

Source: Netflix dataset downloaded from Kaggle.com in CSV format.

Tool Used: Power BI Desktop.

Import Method: Use “Get Data” > “Text/CSV” to load the dataset.



---

- Step 2: Data Cleaning (Excel and Power Query Editor)

Once data is loaded, enter Power Query Editor to clean it:

2.1 Remove Null or Irrelevant Data

Remove rows with null values in essential columns: title, type, country, release_year, duration, director.


2.2 Standardize Column Names

Rename columns for consistency, e.g., release_year to Release Year, show_id to Show ID.


2.3 Split Columns

Duration column: Split into duration_time and duration_type (e.g., "90 min" into 90 and "min").


2.4 Handle Multiple Values

For columns like director and country with multiple entries separated by commas:

Use Split Column by Delimiter.

Or choose to keep only the first value for simplicity.



2.5 Convert Data Types

Convert columns like release_year to whole numbers, date_added to Date/Time.


2.6 Create New Columns

Extract year from date_added for trend analysis.

Create a column like Show Length Category (e.g., Short, Medium, Long) if analyzing duration.



---

- Step 3: Data Modeling

Relationships: If multiple tables are used (e.g., ratings, countries), define relationships using Manage Relationships.

DAX Measures:

Total Shows = COUNT(show_id)

Total Movies = CALCULATE(COUNT(show_id), FILTER(data, data[type] = "Movie"))

Total Directors = DISTINCTCOUNT(director)

Use measures for count by type, rating, or year.




---

- Step 4: Report Visualization Setup

Apply a Dark Theme (custom or default) and arrange your visuals:

4.1 Filters

Use slicers for:

Show Type

Release Year

Country



4.2 Key Visuals

Total Card KPIs: Total Shows,Tv shows, Movies, Directors

Bar Chart:

Country with Total Shows

Total Directors by Type


Donut Chart:

Shows by Type


Line or Area Chart:

Release Year vs Count of Shows


Bar Chart:

Longest Shows by Duration


Rating Distribution:

Bar chart of shows by rating




---

- Step 5: Format and Polish

Use consistent font and colors (red, black, white for contrast).

Add borders and shadows for modern look.

Adjust chart titles, axis labels for clarity.

Enable tooltips for interactivity.



---

- Step 6: Final Checks

Test slicers: all visuals should respond interactively.

Check filter interactions.

Publish to Power BI service (optional) via File > Publish > Power BI Service.

![Image](https://github.com/user-attachments/assets/93cbdd9f-75ed-4332-b2eb-6b2882152f55)oard

