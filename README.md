# CloudWalk

# Database  

Scripts and More Information -> [link ](https://github.com/GuiilhermeLorenzetti/CloudWalk/tree/main/Database)

### Structure:

My approach here was to build an architecture where:

**Bronze:** This is the original CSV file received, which remains stored as the original source.

**Silver:** The same content from the CSV (1:1 compared to the Bronze layer), but now inserted into the database.

**Gold:** Cleaned and structured tables ready to be used in the dashboard.

Since this is a small file, there was no need for full normalization in Power BI or the formal creation of fact and dimension tables. I chose this approach to demonstrate the workflow that would be followed with larger and more complex files in day-to-day scenarios.

Therefore, the file undergoes cleaning and normalization during the transition from the Silver to the Gold layer. Only the Gold layer tables are used in the dashboard, applying relevant business rules. The Silver layer is treated as the source of truth and can be reused in other projects.

