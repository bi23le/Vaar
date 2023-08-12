# Vaar Markdown Notebooks

## Introduction:
Health data provides important insights to improve patient care. However, data is typically not research-ready with high missingness levels.  This Notebook, to help evaluate data imputation efforts, is one of the outputs of an MSc Research Project for Computer Science with Data Science at the University of Sunderland. 

Vaar is an Orcadian sailing term meaning to guide or direct (Orkney is well known for its wild seas); and Vaar also conveys the variable nature of data. The Vaar Notebook is based upon consensus for missing data good practice, as well as statistical data experiments undertaken for the MSc project:  
- Reason for missingness is an important first step  
- Complete case analysis (CCA) is usually only appropriate if data is missing completely at random (MCAR)  
- Outliers often represent valuable information that must not be discarded  
- Normalisation reduces bias from skewed data in downstream models  
- Scaling allows models to compare relative relationships between data points more effectively  
- Multiple Imputation outperforms CCA when missingness is greater than 10%  
- Missing data patterns and information from auxiliary variables impact imputation effectiveness  
- Sensitivity analyses should be conducted with different methods  
- Missingness greater than 50% often results in poor models  


## Description:
There are two R Markdown templates, produced for an MSc project, one in Python and one in R that will return:
- Whether data is MCAR or MAR/MNAR
- A recommended missing data approach which also accounts for indicative model result stability
- An evaluation of imputation efforts against a test model

Coding experience of R or Python is necessary, as due to the variability of data it is expected that additional code blocks will need to be included. RStudio was used to create the templates and there are R Markdown extensions available in Visual Studio Code also.

### View Python Exemplar Web Pages
- [Breast Cancer Wisconsin Original] (https://rpubs.com/bi23le/1070978)

### View R Exemplar Web Pages
- [Breast Cancer Wisconsin Original] (https://rpubs.com/bi23le/1070975)
- [Cervical Cancer Risk Factors] (https://rpubs.com/bi23le/1070977)

Code blocks can be copied and pasted from the markdown templates and exemplars. To use the full notebooks, the following packages are required:

### Python Libraries Required:
- pandas to read in data
- numpy for summary statistics
- seaborn and matplot lib for visualisation
- r-naniar (see below)
- scipy - numpy extension for skew
- sklearn for imputation, model, metrics and minmaxscaler

#### R Libraries Required for Python version:
- Reticulate so both Python and R environments available
- naniar for MCAR test
- rpart and rpart.plot for proportion missing data integration with naniar
Please note: you will also need to preview the file to knit together the two environments, for R to access the python objects.

### R Libraries Required for R version:
- data.table to read in data
- tidyverse to rename variables and tidy data
- janitor to clean variable names
- naniar for MCAR Test and other missing data functions
- visdat to visualise missing data
- ggplot for visualisation
- GGally for pairs ggplot extension
- psych for skew function
- rpart and rpart.plot for proportion missing data integration with naniar
- mice for fluxplot and multiple imputation
- caret for correlation and confusion matrix
- randomForest (optional: example included in template)

#### Step 1: Read data

#### Step 2: Tidy data

#### Step 3: Visualise data and run MCAR Test

#### Step 4: Set key variable values:
        MCAR Test p-value (or 'error' if data singular)
		Yes or No for likelihood variable if data more likely to be missing from some variables
		Yes or No if data missing from dependent variable(s) only
		Proportion of data missing overall as float (automatically set in Python version)

#### Step 5: Visualise variable importance for predicting missingness
		Identify variable that will be used in delta adjustment: variable with missing data nearest the top of the tree

#### Step 6: Create complete case and imputed datasets

#### Step 7: Conduct MNAR Sensitivity Test
		Create imputed dataset with highest delta adjustment
		Optional step to remove outliers

#### Step 8: Select Features
		Optional step to transform data (some data already scaled)

#### Step 9: Build and Test Models (CCA, Imputed, Imputed Delta)
		Create Test and Training data for each
		Set variable value CCA or MI for better_model
		Set variable value Yes or No for delta_impact

#### Lastly: Run 3 code blocks to print summaries:
		MCAR or MAR/MNAR Hypothesis
		Recommended approach for missing data
		Model evaluation
		

## License:
MIT License

Copyright (c) [2023] [Amanda Harris]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
