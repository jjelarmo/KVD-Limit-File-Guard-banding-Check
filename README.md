# KVD-Limit-File-Guard-banding-Check
KVD is an Automatic Test Equipment (ATE) used for IC testing. To compare the measurement reading of each IC whether it is passing or not, the reading must fall between the test limits.

Standard test manufacturing flow have each unit undergo two testing -- Final Test (FT) and Quality Assurance (QA). 
Proper test limits based on manufacturing standards have to apply proper guardbanding wherein the Final Test limits are tighter in specifications. This is to ensure that the bad parts are already screened out during Final Test. 

This project aims to check if proper guardbanding is applied when comparing FT to QA test limits:
Here is the logic of the script:
1. Open all limit files
2. Extract test name only. Then create nested lists: the first index is for the file, second index is for the testname
3. Match files in 2 entries for common testnames. Create a list for merged test names
4. Find test elements and extract full electrical test information. Create a dictionary: keys - testname, values - bin information in list
5. Update dictionary with FT and QA limits
6. Write updated dictionary in excel
7. Compare limits and put flag on limits - 0 if proper guardband is applied; 1 if improper guardband
