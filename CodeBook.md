# Introduction

The script `run_analysis.R`performs the 5 steps as required .

* First,the tranining and test data is merged using the `rbind()` function for each of x,y and subject data. 
* Then, only those columns with the mean and standard deviation measures are taken from the previous datasets. After extracting these columns, they are given the correct names, taken from `features.txt`.
* We take the activity names and IDs from `activity_labels.txt` and they are substituted in the above datasets.
* The columns with vague column names are corrected.
* Finally, we generate a new dataset with all the average measures for each subject and activity type (30 subjects * 6 activities = 180 rows). The output file is called `clean_data.txt`.

# Variables

* `x_train`, `y_train`, `x_test`, `y_test`, `subject_train` and `subject_test` contain the data from the downloaded files.
* `x_data`, `y_data` and `subject_data` merge the previous datasets to further analysis.
* `features` contains the correct names for the `x_data` dataset, which are applied to the column names stored in `mean_std_fts`, a numeric vector used to extract the desired data.
* A similar approach is taken with activity names through the `activities` variable.
* `all_data` merges `x_data`, `y_data` and `subject_data` in a big dataset.
* Finally, `averages_data` contains the relevant averages which will is stored in a `averages_data.txt` file. `