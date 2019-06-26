# What we want to do

 - create ready-to-use templates for use for most common outbreak response scenarios
 - create educational materials to go along with these templates

# Data guides the emergency response

 - collect data (count data)
 - produce basic summary statistics
   - incident curve
   - 2x2 tables (cross-tabulations)
   - Basic summary tables
 - inform decisions for strategic intervention

# Role of epidemiologist

 - Emergency and outbreak response:
   - Population counting;
   - Establishing community based surveillance;
   - Identifying risk factors for infection;
   - Medical data analysis to better target interventions;
 - Surveillance
   - Community based surveillance
   - Indicator based surveillance
   - Event based surveillance
 - Surveys
   - Retrospective mortality; 
   - access to care; 
   - vaccination coverage
   - malnutrition
 - Operational research
 
# Where are the gaps for a field epi?

 - Data collection
   - Messy and incomplete data
 - Data analysis
    - Software license costs and management on high turnover of laptops
    - Different formats of excel spreadsheets
    - Limited automated analysis on current HIS
    - Different data analysis programmes: SPSS, Epi Data, Epi Info, STATA, R, SAS...
    - Lack of consistency 🡪 One Epi=One Method
    - Methods sometimes wrong, but discovered too late
    - Complex presentation of simple analytical outputs
    - Lack of time to learn how to code
 - Translating data into practice/health programming
    - What does a measles vaccination coverage of 60% mean?
 - Supervision and technical support
    - Time to train/supervise all required aspects is limited

# Switching to R

## Benefits

 - No licensing fees!
 - Newer epis are already coming in with some training in R
 - Automated reports with RMarkdown

## Drawbacks

 - Steep learning curve for newbies
 - Currently no support network among epis
 - No one clear method for analyses

# Implementation

 - Identify priority projects based on frequency in MSF settings, most standard
   possible data
    - Cholera
    - Measles
    - Meningitis
    - Acute Jaundice Syndrome
 - MSF Ethical Review Board pre-approved Surveys
    - Malnutrition
    - Vaccination Coverage
    - Retrospective mortality access to care

# Necessary players

## MSF

 - Field epidemiologists with experience to direct and review template
   construction.

## RECON

 - R programmers with technical knowledge.

# Challenges and pain points

 - Installing R and R packages
 - Analyses that were missing or not-quite-there (aweek, srvyr)
 - Analysts attempting to convert tidyverse code to a package context
 - How do you test templates?
 - Package dependencies. 

# Constant feedback

 - Develop templates and release to field epi to test on real-world data
 - collect feedback
 - improve templates based on feedback

# Virtual hackathons

 - online interaction between field epis and developers
 - what worked?
 - what didn't?

# Future steps

 - video tutorials on R and these templates from Greg Martin
 - release of the templates on CRAN
 - release of templates on drat repository for quick fixes 

