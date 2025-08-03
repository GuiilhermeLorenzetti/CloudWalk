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


# Report

More Information -> [Link](https://github.com/GuiilhermeLorenzetti/CloudWalk/tree/main/Report)

The report does not include any transformations in Power Query, with the goal of keeping the model lightweight and centralizing complexity and business rules in the database, where they can be better controlled and reused.

The only transformation applied in Power Query was an adjustment to the column names, making them more readable and suitable for a Self-Service BI environment, facilitating navigation and understanding for end users.

The dashboard was designed with a logic that highlights key indicators at first glance, while also allowing deeper exploration if needed, using both visuals and analytical tables.

You can find a more detailed description of the visuals, an explanatory video, and the PBIX file at the link provided above.

## Considerations on the Analysis

All mandatory questions requested in the challenge can be answered through the developed report. In addition, it also addresses common needs such as aggregations, averages, and basic distribution analyses.

## Limitations and Highlighted Insights

Due to the simplicity of the dataset, deeper or more complex analyses were limited. Still, some relevant patterns are worth highlighting:

1. **Legal Entities (PJ) transact more than Individuals (PF)**  
Legal entities dominate both in total transaction value and transaction frequency.  
This suggests distinct behavioral profiles between PF and PJ, indicating that strategic actions and analytical models should treat them separately.

2. **POS vs. TAP by Entity Type**  
POS transactions are largely dominated by legal entities (PJ) in absolute value.  
On the other hand, TAP is much more commonly used by individuals (PF):  
PF transacts approximately 4.59 billion via TAP, compared to around 1.58 billion by PJ.  
This behavior may be related to the informality and ease of using TAP via mobile devices among individuals.

3. **Anticipation Method and Nitro/D0**  
There are differences in average ticket size and merchant base depending on the anticipation method selected.  
This suggests that the choice of anticipation method is associated with the user’s or merchant’s transactional profile.

4. **Most Profitable Segments**  
PJ in the "normal" price tier represents the majority of the total transacted value.  
However, there are growth opportunities in other segments, such as:  
PF using TAP, where strategies could focus on increasing average ticket size or transaction frequency.

5. **Stability Over Time**  
The time series did not show any abrupt spikes or drops.  
This may indicate operational stability or highlight the need for more sensitive methods to detect subtle variations.


