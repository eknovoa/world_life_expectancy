# world_life_expectancy

This is a data analytics project I worked on within the MySQL Data Analytics Course with Analyst Builder.

The goal of this project was cleaning data with SQL.

Initiate Project
1. Create a new schema in MySQL Workbench, based on the course, it was called world_life_expectancy.
2. Double-click on the world_life_expectancy database so that you are working with that database on MySQL Workbench.<br>
   <img width="204" alt="Screenshot 2025-03-05 at 6 44 41 PM" src="https://github.com/user-attachments/assets/8ed60cf6-ec85-421e-9d6f-cbb2dd91542c" />
3. If on a Mac, open the sql script, "WorldLifeExpectancyScript.sql" file and run the query so that the table will be created.
4. If on a Windows, you can import the table using Table Data Import Wizard.<br>
   <img width="260" alt="Screenshot 2025-03-05 at 6 46 05 PM" src="https://github.com/user-attachments/assets/da9b2c36-82a2-4a71-84f1-ef6b71e3a792" />
5. Be sure to click "Refresh All" to refresh the database and table with the new changes.<br>
   <img width="218" alt="Screenshot 2025-03-05 at 6 47 09 PM" src="https://github.com/user-attachments/assets/d2cda8a4-00fc-47e0-99c3-cb323bc34c52" />

Cleaning Steps:
1. I started by renaming the table from worldlifexpectancy to World_Life_Expectancy, and I also renamed the majority of the table's columns to reflect lowercase and snake_case naming convention. You case see the query for this inside the file, "rename-table-columns".
2. I checked for duplicate rows based on country and year columns. I did this sql code differently than the project did in the course. Please see file, "remove-duplicates". I identified that these three countries had duplicate rows: Ireland, Senegal, and Zimbabwe.<br>
   <img width="183" alt="Screenshot 2025-03-05 at 7 00 02 PM" src="https://github.com/user-attachments/assets/7ad5b02a-0ab9-4100-8fe4-2fe98410a855" />
3. Before removing the duplicates that I identified based on the row_id per country. I created a backup table so that we would have an original table that remains untouched and the second table I can delete duplicate rows safely.
4. Dealt with missing data in the status column, only a few rows in certain countries needed to be categorized as "developing" or "developed". Then we fixed the missing data for the life_expectancy column. By taking the year prior and after the year with the missing data, and taking the life_expectancy of each of those years to find the average and populate the missing row in that column with the value from the calculation. The SQL statements can be found in the following file: missing-data
