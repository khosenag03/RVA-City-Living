# RVA-City-Living

What this project is about and what it aims to accomplish?

  We will web-scrape apartment sites in RVA to provide a resource for clients that compare the cost of living and public education by zip code.

Explain the problem that the project addresses specifically.

  Richmond, Virginia, is quickly becoming a city of choice. Many who relocated to RVA are often tasked with searching several sights to gather information that one would need when looking for a residence. This collection of data will be of convenience to those seeking to gather information that would guide an informed decision about what area of RVA best meets their needs.

What evidence is there to support the need for this project?

  To assist users who are in pursuit of reasonably priced living and adequate school ratings. 

EXTRACT (Objects to Pull):
  Apartment Data (Apartments.com)
    Residence Name
    Address Link
    Zip Code
    Leasing Contact: Phone
    Local Education
      School Name
      Grade Levels
      Type: Public or Private
      School Number
    Starting Price Range
    Parking Included
  Population Demographic Data by Zip Code (factfinder.census.gov)
    Gender
    Age
    Citizens of Voting Age (18+)
    Race

TRANSFORM (data cleaning and transformation):
  Apartments.com
    Used .replace to reassign labels/values to documents
    Organized scraped information into a dictionary to be merged with census data
    Factfinder.census.gov
  Pandas
    Used Pandas to drop both null values to empty columns,  and renamed columns.
    Turned census csv into DataFrame and 
    Removed redundant fields, 
    Renamed fields, 
    Dropped N/A values and 
    Converted DataFrame into html table to append dictionary

LOAD (database/tables/collections):
  The final database 
    “Apartments_db” in MongoDB
  Table
    “Apartments”		
  Rationale
    With there not being a common denominator between the apartment information and the demographic information, a relational database would not be the proper tool to use for our loading process.  Therefore, MongoDB was our best load option

