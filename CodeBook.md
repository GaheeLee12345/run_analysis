CodeBook for run_analysis.R
============================

The "run_analysis.R" script follows the following steps:

1. It will loads the zipped data files from the (http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones) link and put it in a directory named "HAR" (if required, it will create the directory). Then unzips the zip file.
2. First, reads teh features and filter only the features that contain "mean()" and "std()".
3. Then, it will load all train and test data but only the filtered features. IT will use negative widths in "read.fwf" to skip the columns that are not required. That makes it much faster to load and process.
4. It will merge the subject files to main dat anad then merges all train, and test data (using rbind). The result is a dataframe named "all_data". It also label the columns by the name of the features.
5. The net step creates another dataframe named "all_average" that contains the mean of all columns by "subject". I have used "aggregate" function for that. 
6. Last step, it to write both dataframes into CSV files. 
