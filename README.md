# KVD-Limit-File-Guard-banding-Check
KVD is an Automatic Test Equipment (ATE) used for IC testing. To compare the measurement reading of each IC whether it is passing or not, the reading must fall between the test limits.

Standard test manufacturing flow have each unit undergo two testing -- Final Test (FT) and Quality Assurance (QA). 
Proper test limits based on manufacturing standards have to apply proper guardbanding wherein the Final Test limits are tighter in specifications. This is to ensure that the bad parts are already screened out during Final Test. 

This project aims to check if proper guardbanding is applied when comparing FT to QA test limits:
Here is the logic of the script:
1. open all limit files
2. extract test name only. create nested lists: the first index is for the file, second index is for the testname
3. match files in 2 entries for common testnames. create a list for merged test names
4. find test elements and extract full electrical test information. create a dictionary: keys - testname, values - bin information in list
5. update dictionary with FT and QA limits
6. write updated dictionary in excel
7. compare limits and put flag on limist with no guardband
