# slide-seq_spatial_analysis
Pipeline for spatial analysis of slide-seq data
Edited: 8/02/19<br>

There are three functionalities contained in these notebooks:
1. Visualize Slide-seq data in a notebook.
2. Run analysis to determine if a gene is being expressed spatially differently within a cell type
3. Run analysis to determine if there is a correlation between the expression of two genes. 

The following are instructions for each of these functionalities. 

For each functionality, the pipeline starts with the following steps: 

1. Run your data through NMFReg.ipynb
2. Choose your method:

#### Note: Data for the following methods will be stored in the folders specified in NMFReg.ipynb.

## 1. Visualizing Slide-Seq Data

1. Go into the data_visualization folder and select the notebook for the puck you want (or, change the filepath and puck number to reflect your own puck. 
2. Run each chunk of the code to get to the interactive plot. Directions for how to use the interactive plot can be found in the notebook. 

Note: To create a new notebook, click the checkbox next to one of the other notebooks and select "duplicate". In the copied notebook, change the name of the notebook and the pkn variable to your desired puck. 

## 2. Single Gene Expression

Go to PermutationTest_Expression.ipynb and follow the instructions in that notebook. 
(The PermutationTest_Expression_kstest.ipynb runs the same analysis, but calculated p-values and effect size using the Kolmogorov–Smirnov test.)

You can also examine how many beads will yield a significant result with this method using the PermutationTest_Expression_power_analysis.ipynb. (This not implemented for the Kolmogorov–Smirnov test method.)

## 3. Two Gene Expression Correlation

Go to PermutationTest_Coexpression.ipynb and follow the instructions in that notebook.

You can also examine how many beads will yield a significant result with this method using the PermutationTest_Coexpression_power_analysis.ipynb.

# File Descriptions

1. NMFreg.ipynb: Initial analysis of slide-seq data. Assigns beads to clusters using non-negative matrix factorization. Saves normalized data and cluster assignments to .csv files to be used in other methods. 
2. data_visualization folder: Contains .ipynb notebooks to visualize kidney puck data.
3. PermutationTest_Expression.ipynb: Method to test if a gene is being expressed non-randomly within a given region or cell type.
4. PermutationTest_Expression_kstest.ipynb: Method to test if a gene is being expressed non-randomly within a given region or cell type. This is the same as PermutationTest_Expression.ipynb except that p-value and effect size are calculated using a Kolmogorov–Smirnov test.
5. PermutationTest_Expression_power_analysis.ipynb: Analysis to test how many beads the gene should be expressed in to yield a significant result. (Not implemented for Kolmogorov-Smirnov test)
6. PermutationTest_CoExpression.ipynb: Method to test if the expression of two genes is correlated within a given region or cell type.
7. PermutationTest_CoExpression_power_analysis.ipynb: Analysis to test how much noise can be added to the puck while still yielding a significant result and an effect size that indicates correlation. 
