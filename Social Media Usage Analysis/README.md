Social Media Usage Analysis Dashboard | Power BI

Project Overview

This project is an interactive Social Media Usage Analysis Dashboard built in Microsoft Power BI using the Time-Wasters on Social Media dataset.
The report explores how users interact with social media platforms and examines the relationship between time spent, engagement, content consumption, productivity loss, self-control, satisfaction, addiction level, and user demographics.
The dashboard is organized into four analytical pages so that users can move from a high-level usage overview to deeper behavioral and demographic insights.

Dashboard Pages

1. Usage Overview
Provides a high-level summary of overall social media usage patterns.

KPIs:-
Total Users
Average Time Spent
Average Sessions
Average Videos Watched

Visuals:-
Average Time Spent by Platform
Users by Platform
Users by Device Type
Average Videos Watched by Frequency
Users by Watch Reason

Filters:-
Frequency
Video Category
Location
Connection Type
Platform

2. Content & Engagement Analysis
Examines how content type and viewing behavior relate to user engagement.

KPIs:-
Average Engagement
Average Scroll Rate
Average Video Length
Top Video Category

Visuals:-
Videos Watched by Video Category
Time Spent and Engagement by Platform and Video Category
Videos Watched by Watch Reason
Watch Reason Distribution

This page helps identify which content categories and viewing motivations are associated with higher engagement and consumption.

3. Productivity & Addiction Analysis
Focuses on the behavioral impact of social media usage.

KPIs:-
Average Addiction Level
Average Satisfaction
Average Productivity Loss
Average Self-Control

Visuals:-
Time Spent and Addiction Level by Video Category and Frequency
Productivity Loss by Profession
Satisfaction by Platform
Self-Control by Age

This page explores whether heavier usage is associated with addiction, reduced self-control, and productivity loss.

4. User Demographics & Behavior
Analyzes how social media behavior varies across different user groups.

KPIs:-
Top Profession
Top Location
Average Income
Average Age

Visuals:-
Users by Location
Users by Gender
Users by Connection Type
Average Time Spent and Average Age by Platform
Average Income by Profession

This page provides a demographic view of social media usage and helps identify differences across locations, professions, age groups, and platforms.

Data Model

The Power BI model contains two tables:

Time-Wasters on Social Media — main analytical dataset
Measure Table — dedicated table for DAX measures

The dataset is kept as a single analytical table because each row represents a user-level social media usage observation rather than a repeated transactional event.

Key Measures:-
The report includes measures such as:

Total Users
Avg Time Spent
Avg Sessions
Avg Videos Watched
Avg Engagement
Avg Scroll Rate
Avg Video Length
Top Video Category
Avg Addiction Level
Avg Satisfaction
Avg Productivity Loss
Avg Self Control
Top Profession
Top Location
Avg Income
Avg Age

Key Business / Analytical Questions

The dashboard helps answer questions such as:
Which social media platforms have the highest average usage?
Which platforms have the largest user base?
What devices are most commonly used for social media?
Why do users consume social media content?
Which video categories receive the most consumption?
How does time spent on videos relate to engagement?
Which professions experience the highest productivity loss?
Is higher social media usage associated with higher addiction levels?
How does self-control vary across age groups?
Which platforms have the highest user satisfaction?
How does social media behavior vary by gender, profession, income, and location?

Power BI Features Used:-
Data Cleaning and Transformation
DAX Measures
KPI Cards
Bar and Column Charts
Donut and Pie Charts
Scatter Charts
Treemap
Line Chart
Map Visual
Slicers
Page Navigation
Buttons and Icons
Bookmark-Based Filter Panel
Reset Filters Bookmarks
Interactive Cross-Filtering
Dedicated Measures Table

Tools Used:-
Microsoft Power BI Desktop
Power Query
DAX
Data Visualization
Data Analysis

Repository Structure

social-media-usage-analysis/
│
├── Social Media Usage Analysis.pbix
├── README.md
│
└── images/
    ├── usage-overview.png
    ├── content-engagement-analysis.png
    ├── productivity-addiction-analysis.png
    └── user-demographics-behavior.png


How to View the Dashboard

The report is provided as a Power BI Desktop file.

Download Social Media Usage Analysis.pbix.

Install Microsoft Power BI Desktop if required.

Open the .pbix file.

Navigate between report pages and use the slicers, filters, buttons, and interactive visuals to explore the analysis.

Skills Demonstrated

This project demonstrates practical skills in:

Power BI Dashboard Development
Data Cleaning
DAX
KPI Development
Behavioral Data Analysis
User Engagement Analysis
Productivity Analysis
Demographic Analysis
Data Visualization
Interactive Report Design
Dashboard Navigation and Bookmarks

Project Goal

The goal of this project is to go beyond basic platform popularity analysis and explore how social media consumption patterns relate to engagement, productivity, self-control, satisfaction, and addiction.

Author

Mohamed Fahad
Aspiring Data Analyst
