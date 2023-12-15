# Instructions to process data

The original data are too heavy to share using git so they are not versioned. They can be obtained from:

-   Link to the data: [data-raw](https://mcmasteru365-my.sharepoint.com/:u:/r/personal/dossanb_mcmaster_ca/Documents/RSAccess/data-raw.rar?csf=1&web=1&e=yVzKvO)

These data are stored in the "data-raw" folder, and the files are organized based on their extensions:

-   *vectors*: Shapefiles composed of five separate files: .shp (main file), .shx (index file), .prj (projection definition file), .dbf (dBASE table file), and .cpg (codepage for identifying the character set to be used).

-   *rasters*: Satellite images with a .tif extension.

-   *csvs*: Comma-separated-values files.

Within each these folders, the files are divided into input data and output data. To process the data, the following notebooks need to be executed:

+--------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| Step                                                                     | Notebooks                                                                                                                                                                                                                 |
+==========================================================================+===========================================================================================================================================================================================================================+
| To extract attributes from the satellite imagery and other spatial data. | -   *1a_feature_extraction.qmd*: Mostly Python code for extracting satellite images and road network attributes. The data are processed, and the output is some new datasets with variables saved in the "output" folder. |
|                                                                          |                                                                                                                                                                                                                           |
|                                                                          | -   *1b_feature_extraction_SAM.qmd*: Mostly Python code for extracting job accessibility attributes. The data are processed, and the output is a new dataset with variables saved in the "output" folder.                 |
+--------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| To perform the data analysis applied to the dataset.                     | -   *2_pca_and_cluster.Rmd*: R code for conducting PCA analysis followed by clustering classification to identify spatial patterns.                                                                                       |
|                                                                          |                                                                                                                                                                                                                           |
|                                                                          | -   *3_job_accessibility_comparisons.Rmd*: R code for evaluating differences in job accessibility between the spatial patterns identified in the previous step.                                                           |
+--------------------------------------------------------------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

As the data has been downloaded and inserted into the correct folder (data-raw), it is not necessary to run the above notebooks in the order indicated by the numbers. You can only run the data analysis notebooks because all the necessary datasets are in the vectors and csvs folder.

Subsequently, run:

-   *make-data.qmd*: R code that reads selected output shapefiles and saves them to the "data" folder in R format.
