# Data Cleaning

Manual Data Cleaning includes:

- Retyping incorrect data
- Copying and pasting columns and rows
However, manual cleaning is inefficient, error-prone, and demoralizing. So never clean manually.

Programmatic Data Cleaning uses code to:

- Automate cleaning tasks
- Minimize repetition
- Save time
Data wrangling takes a tremendous amount of time for the data professional, so doing anything that saves time is great.

## Getting Ready To Clean

The very first thing to do before any cleaning occurs is to make a copy of each piece of data. All of the cleaning operations will be conducted on this copy so you can still view the original dirty and/or messy dataset later. Copying DataFrames in pandas is done using the `copy` method. If the original DataFrame was called `df`, the soon-to-be clean copy of the dataset could be named `df_clean`.

## The Cleaning Process

Programmatic data cleaning is a separate process within data wrangling. It has three steps:

1. Defining
2. Coding
3. Testing

### Define

The first step is to define a data cleaning plan in writing by converting your assessments into cleaning tasks by writing little how-to guides. This plan also serves as documentation so that your work can be reproduced.

### Code

Second, you'll translate these words to code and actually run it.

### Test

Finally, you'll test your dataset often using code to make sure your cleaning code worked. This is like a revisiting the assess step.

## Missing Data

When checking data quality, it is usually best to deal with completeness issues first. For missing data this means:

- Concatenate
- Join
- Impute, if possible
It's important to do this upfront so that subsequent data cleaning will not have to be repeated.

## Address Tidiness After Structural Issues and Before Content Issues

After addressing missing data the next logical step is cleaning for tidiness. Statistician, Hadley Wickham, is the pioneer of tidy data, and in his paper, 'Tidy data' (The Journal of Statistical Software, vol. 59, 2014), he makes these key points:

- Tidy datasets are easy to manipulate
- Tidy datasets with data quality issues are almost always easier to clean than untidy datasets with the same issues

This means it's generally best to clean structural issues first, like tidiness, and then clean content issues, like quality.
