 

# HR Diversity & inclusion

## Table of Contents
- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Tools](#tools)
- [Data Preparation/Cleaning](#data-preparationcleaning)
- [Data Visualization](#data-visualization)
- [Data Analysis](#data-analysis)
- [Results/Findings](#resultsfindings)
- [Recommendations](#recommendations)


## Project Overview
- Define proper KPIs in hiring, promotion, performance and turnover
- Create a visualisation for the HR manager that reflects all relevant Key Performance indicators(KPIs) and metrics in the dataset.

Calculating the following measures could help to define proper KPIs:

- Number of men
- Number of women
- Number of leavers
- % employees promoted (FY21)
- % of women promoted
- % of hires men
- % of hires women
- % turnover
- Average performance rating: men
- Average Performance rating: women

## Data Sources
data was provided by pwc

## Tools
- Power BI

## Data Preparation/Cleaning

- Changed the header row of dataset
- Replaced the value is New hire FY20? N coverted No and Y converted Yes
- Replaced the value is In base group for turnover FY20 N coverted No and Y converted Yes
- Replaced the value is Promotion in FY20? N coverted No and Y converted Yes
- Removed Unnecessary columns
- Removed Unnecessary rows
- Each of the columns in the table were validated to have the correct data type

## Data visualization 

![Alt](

## Data Analysis

Below are all the measures created:

- #of leavers = CALCULATE(COUNTA('HR Manager'[Employee ID]), 'HR Manager'[Leaver FY] IN { "FY20" })

- #of men =Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[Gender]="Male"))

- #of women = Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[Gender]="Female"))

- % employees promoted (FY21) =Divide(Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[Promotion in FY21?]="Yes")),Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[In base group for Promotion FY21]="Yes")))

- % of hires men = Divide('HR Manager'[# of men],('HR Manager'[# of men]+'HR Manager'[# of women]))

- % of hires women = Divide('HR Manager'[# of women],('HR Manager'[# of women]+'HR Manager'[# of men]))

- % Promotees who were men = Divide(Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[Gender]="Male")),distinctcount('HR Manager'[Employee ID]))

- % Promotees who were women = Divide(Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[Gender]="Female")),distinctcount('HR Manager'[Employee ID]))

- % Turnover = Divide(Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[FY20 leaver?]="Yes")),Divide(Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager','HR Manager'[In base group for turnover FY20]="Y"))+Calculate(distinctcount('HR Manager'[Employee ID]),Filter('HR Manager',NOT('HR Manager'[Department @01.07.2020]=BLANK()))),2))

- Avg Rating Men = Calculate(Average('HR Manager'[FY20 Performance Rating]),Filter('HR Manager','HR Manager'[Gender]="Male"))

-Avg Rating Women = Calculate(Average('HR Manager'[FY20 Performance Rating]),Filter('HR Manager','HR Manager'[Gender]="Female"))

## Results/Findings

-The dashboard shows a balanced diversity effort in terms of target hires, with most departments achieving nearly 50/50 gender representation, except in more senior roles where the male population is higher.

- The average time in job levels indicates that men spend more time in junior roles before being promoted to senior positions, whereas women are promoted more quickly to higher levels.

- Promotion rates for women are lower compared to men, suggesting there could be underlying bias or structural barriers in career progression.

- Turnover rates are highest in the sales and marketing departments and are particularly high among younger employees, which may indicate dissatisfaction or lack of growth opportunities in these areas.

- Women make up a higher percentage of recent hires, but their turnover rate is concerning, particularly in technical roles where they remain underrepresented.

## Recommendations

- Increase mentorship and leadership development programs aimed at women in junior and mid-level positions to balance the promotion rates between genders.

- Analyze the high turnover rates in sales and marketing departments to understand the underlying causes and address any issues related to job satisfaction, career growth, or work-life balance.

- Encourage greater retention of women in technical roles by providing more opportunities for career development and creating a more supportive working environment.

- Introduce additional programs to retain younger employees, such as clear career advancement paths or job enrichment opportunities

 
