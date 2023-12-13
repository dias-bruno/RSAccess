# Instructions to process data

The original data are too heavy to share using git so they are not versioned. They can be obtained from:

-   Link to raw-data: **INSERT LINK HERE**

These data are stored in the "raw-data" folder, and the files are organized based on their extensions:

-   *vectors*: Shapefiles composed of five separate files: .shp (main file), .shx (index file), .prj (projection definition file), .dbf (dBASE table file), and .cpg (codepage for identifying the character set to be used).

-   *rasters*: Satellite images with a .tif extension.

-   *csvs*: Comma-separated-values files.

Within each these folders, the files are divided into input data and output data. o process the data, the following notebooks need to be executed:

-   *1a_feature_extraction.qmd*: Mostly Python code for extracting satellite images and road network attributes. The data are processed, and the output is some new datasets with variables saved in the "output" folder.

-   *1b_feature_extraction_SAM.qmd*: Mostly Python code for extracting job accessibility attributes. The data are processed, and the output is a new dataset with variables saved in the "output" folder.

-   *2_pca_and_cluster.Rmd*: R code for conducting PCA analysis followed by clustering classification to identify spatial patterns.

-   *3_job_accessibility_comparisons.Rmd*: R code for evaluating differences in job accessibility between the spatial patterns identified in the previous step.

Subsequently, run:

-   *make-data.qmd*: R code that reads selected output shapefiles and saves them to the "data" folder in R format.
