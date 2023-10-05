# Netflix Dataset Analysis Report
## Introduction
In this report, we will perform a comprehensive analysis of the Netflix dataset obtained from Kaggle. The goal is to prepare and clean the data, perform some basic transformations, and create visualizations to gain insights into the dataset. The report will be divided into several sections, each covering a specific aspect of the analysis process.
## Dataset Download
The first step is to download the Netflix dataset from Kaggle. You can access the dataset using the following link: Netflix Dataset on Kaggle. Follow the instructions on the Kaggle page to download the dataset as a zip file.
1.	Navigate to the provided Kaggle link.
2.	Click the "Download" button to obtain the dataset in a zip file format.
## Data Preparation in Excel
### Step 1: Initial Data Cleanup
After downloading the dataset, it's essential to start with some basic data cleaning in Excel.
1.	Open the zip file and extract the dataset.
2.	Launch Microsoft Excel and open the dataset.
### Step 2: Extracting Descriptions
The dataset contains a lengthy "description" column. We'll extract this column and place it in a separate sheet.
1.	Highlight the entire "description" column.
2.	Cut (Ctrl+X) the selected data.
3.	Create a new sheet in Excel.
4.	Paste (Ctrl+V) the copied data into the new sheet.
5.	Rename this new sheet as "Descriptions."
### Step 3: Splitting Columns
Several columns like "cast," "directors," "listed_in," and "countries" contain multiple values separated by commas. We'll split these columns into separate sheets to facilitate further analysis.
For the "cast" column:
1.	Copy the entire "cast" column.
2.	Paste it into the next available column in Excel.
3.	Delete the original "cast" column.
4.	Highlight the newly pasted "cast" data.
5.	In the "Data" tab, select "Text to Columns."
6.	Choose the "Delimited" option and select "Comma" as the delimiter.
7.	Click "Finish" to split each cast member into its own column.
8.	Name the new columns as "cast_1," "cast_2," and so on.
Repeat the same process for the "directors," "listed_in," and "countries" columns.
### Step 4: Data Trimming
After splitting the columns, it's crucial to trim any leading or trailing spaces in the data.
1.	Create a new sheet for each split column (e.g., "Cast," "Directors," "Listed In," "Countries").
2.	In the new sheet, apply the "TRIM" formula to remove extra spaces from the data.
3.	Copy the trimmed data and paste it as values (right-click, "Paste Values") to replace the original data.
4.	Rename the new sheets accordingly.
### Step 5: Creating Relationships
To maintain data integrity, establish relationships between the sheets based on the "show_id" column. This will facilitate data aggregation in the future.
1.	Copy the "show_id" column from the "Descriptions" sheet.
2.	Create new Excel files for each sheet created during the split operation (e.g., "Cast," "Directors," "Listed In," "Countries").
3.	Paste the "show_id" column into the new Excel files.
4.	Save each sheet as a separate Excel file for importing into MySQL Workbench.
## MySQL Workbench
### Step 1: Database Setup
1.	Open MySQL Workbench and create a new connection named "Netflix Dataset."
2.	Test the connection to ensure it's successful.
### Step 2: Importing Excel Files
1.	Create a new schema named "Netflix_data" in MySQL Workbench.
2.	In MySQL Workbench, open the schema "Netflix_data."
3.	Right-click on "Tables" and choose "Table Data Import Wizard."
4.	In the Notepad application, navigate to the "File" menu and click on "Save As." Under the encoding options, select "ANSI" and save the file. If prompted, choose to replace the existing file. Repeat this procedure for all the Excel files.
5.	Select the Excel files you prepared for each split column and import them one by one.
6.	Repeat this process for all relevant Excel files.
### Step 3: Data Repivoting
To simplify the data structure and create a relationship between show IDs and countries:
1.	In MySQL Workbench, right-click on the "Countries" table.
2.	Choose "Create Table" and rename it to "Countries_released."
3.	Execute the new table creation query to replace null values and extract relevant columns.
4.	Repeat this process for all relevant tables.
### Step 4: Power BI Visualization
1.	Connect Power BI Desktop to the MySQL dataset.
2.	Create relationships between the tables, focusing on the "show_id" column.
3.	Create various visualizations to gain insights from the dataset, such as area charts, stacked column charts, and maps.
4.	Customize the visualizations, titles, and formatting as needed.
## Creating a Dashboard for Movies/TV Shows:
1.	To enhance this sheet, I will introduce some card visualizations. Initially, I will select the card type and drag the "ratings" field from the Netflix dataset Titles.
2.	I'll label this card "Rating" and format it accordingly.
3.	I will replicate this process for the "release year" by dragging the "release" field from the Netflix dataset Titles, naming the card "Release Year," and formatting it accordingly.
4.	Additionally, I will include a card for the "description," but I will disable the title for this card.
5.	To provide more details, I will incorporate multi-row cards that display the names of the cast, directors, and listed categories.
6.	For the cast, I'll follow the same procedure as with the cards, selecting the multi-row card type and dragging the "cast" field from the Netflix dataset Cast.
7.	I'll name this multi-row card "Cast" and apply the same procedure to the "directors" and "listed in" fields for their respective multi-row cards.
8.	I'll label these multi-row cards as "Directed By" and "Listed By."
9.	Lastly, I will add a slicer visualization. Initially, I'll select the slicer type and drag the "titles" field from the Netflix dataset Titles.
10.	I'll customize the slicer's appearance by navigating to the "format visual" option, selecting "slicer settings," choosing the dropdown style, and adjusting the color scheme.
11.	The slicer will be labeled "Movies/TV Shows."
12.	To observe the impact, I will verify the visualizations by selecting any movie in the slicer, which will result in changes across all visualizations:
  *	The map visualization will display the country of origin for the selected movie.
  *	The rating visualization will reveal the movie's rating.
  *	The release year visualization will display the year of release.
  *	The description visualization will provide information about the selected movie.
  *	The cast visualization will list the cast members.
  *	The director visualization will indicate the movie's director.
  *	The listed visualization will show the categories in which the movie is listed.
  *	The slicer visualization will enable the selection of different movies for visualization.

## Country Overview:
1.	A separate sheet is created to visualize the availability of Netflix content worldwide.
2.	The map visualization from the first sheet is duplicated and enlarged.
3.	Data labels are added for clarity.
4.	The title "Netflix Availability Worldwide" is applied to the map visualization.

## Conclusion
In conclusion, this report outlined the steps involved in analyzing the Netflix dataset, from downloading and preparing the data in Excel to importing it into MySQL Workbench and visualizing it in Power BI. The final result is a comprehensive dashboard that provides valuable insights into the Netflix dataset



