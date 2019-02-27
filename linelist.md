<!--

This package is dedicated to simplifying the cleaning and standardisation of
linelist data. Considering a case linelist data.frame, it aims to:

    standardise the variables names, replacing all non-ascii characters with
their closest latin equivalent, removing blank spaces and other separators,
enforcing lower case capitalisation, and using a single separator between words

    standardise the labels used in all variables of type character and factor,
as above

    set POSIXct and POSIXlt to Date objects

    extract dates from a messy variable, automatically detecting formats,
allowing inconsistent formats, and dates flanked by other text

    support data dictionary: linelist objects can store meta-data indicating
which columns correspond to standard epidemiological variables, usually found
in linelists such as a unique identifier, gender, or dates of onset 

-->

Title: Epidemiological Data Standardisation With the Linelist Package

Data stanardisation is a major challenge across all fields. In epidemiology, 
data from outbreaks are collected rapidly in a wide-format excel spreadsheet
called a linelists where each row represents information from a single patient.
Because data are collected rapidly from various sources in different conditions,
the chances for errors is very high, which can have drastic effects on how day
to day decisions are made. Common errors include dates in different formats or
incorrectly formatted, spelling errors, encoding errors, and differing variable
names. As the linelist grows, the ability for a data manager to fix these
errors in excel diminishes. The linelist package provides a framework for
sensible data standardisation for tabular linelist data commonly used in
outbreak analysis. This includes functionality for guessing dates, cleaning
non-standard variable names, standardizing categorical data based on known
rules, and defining a data dictionary for variables. With the help of linelist,
it becomes easier to create robus data pipelines for the generation of automated
reports by catching simple mistakes and reducing the cognitive overhead needed
for standardising a messy data set. 


