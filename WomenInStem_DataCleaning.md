# Capstone Project 1 Data Cleaning

**Title:** A Guide for Female Students with a STEM Major


**Original data:** 

My data was found on the Higher Ed website (https://highered.ipums.org/highered/) and it was in the csv format. The website also offers detailed information about what the columns represent and how the labels reflect real world meanings. With python's pandas package, the data can be read into the system. With the "info" attribute, I found there are 217502 rows and 33 columns in this data file, with a size of 55MB.  


**Spot and treat NAN data** 

There were no null entries in the original data upon initial examination. It appears that this data has been engineered to have assigned non-null values to represent null datas. After reading the documentations, I input those values to the 'na\_values' parameter in the pandas "read\_csv" function. This time when the csv files was imported, the info shows columns with null values. There are several columns with less than 30% of the total rows of valid data available. They physical meanings of these columns are not closely relevant to this study(e.g. 'FNVS' (type of visa), 'CHTOT' (number of children)). These columns were dropped. There are seven columns with the same less-than full number of non null values. 

There are seven columns with the same less-than full number (186020) of non null values. They all appear to relate to the job aspects of the data. When checking the 'LFSTAT' (employment status) column, it shows the same number (186020) of entries were employed and the rest were unemployed. This makes sense that only when an person was employed, these job related questions were recorded to be valid. These data were left as they are. 


**Make entries meaningful**
The 'REFID' column was constist of both number and string data types and it is a different record of the survey ID from the 'PERSONID' column. This info is not closely relevent to this analysis. The 'REFID' column was dropped.   

The data come in a highly engineered format and many entries were catagorized and using numbers to replace real meanings. For example, 'GENDER' column has 1 and 2 to represent female and male, respectively. I used dictionaries to record the numbers and their corresponding physical meanings for most of the columns. These dictionaries were then applied to the orignal columns with the "map" attribute. This will make the EDA and visulization more presentable. 


**Is the data tidy?**

The definition for a tidy data from Hadley Wickham's paper:
1. Each variable forms a column.
2. Each observation forms a row.
3. Each type of observational unit forms a table.
This current data meet all the above requirements. Each column and row are defined for each variable and observation, respectively. There is only one table in this case. This data is prepared to become the tidy data that is ready for EDA. 


