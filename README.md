Food Inspections Evaluation
============================

This is our model for predicting which food establishments are at most risk for the types of violations most likely to spread food-borne illness. Chicago Department of Public Health staff use these predictions to prioritize inspections. During a two month pilot period, we found that that using these predictions meant that inspectors found critical violations much faster.

You can help improve the health of our city by improving this model. This repository contains a training and test set, along with the data used in the current model. 

Feel free to clone, fork, send pull requests and to file bugs. 
Please note that we will need you to agree to our Contributor License Agreement (CLA) in order to be able to use any pull requests.


Original Analysis and Reports
-----------------------------
In an effort to reduce the public’s exposure to foodborne illness the [City of Chicago](https://github.com/Chicago) partnered with Allstate’s Quantitative Research & Analytics department to develop a predictive model to help prioritize the city's food inspection staff.  This Github project is a complete working evaluation of the model including the data that was used in the model, the code that was used to produce the statistical results, the evaluation of the validity of the results, and documentation of our methodology.

The model evaluation calculates individualized risk scores for more than ten thousand Chicagoland food establishments using publically available data, most of which is updated nightly on [Chicago’s data portal]( https://data.cityofchicago.org/). The sole exception is infortmation about the inspectors.

The evaluation compares two months of Chicago’s Department of Public Health inspections to an alternative data driven approach based on the model. The two month evaluation period is a completely out of sample evaluation based on a model created using test and training data sets from prior time periods.

The reports may be reproduced compiling the knitr documents present in ``./REPORTS``.

REQUIREMENTS
------------

All of the code in this project uses the open source statistical application, R.  We advise that you use ```R version >= 3.1``` for best results. 

The code makes extensive usage of the ``data.table`` package. If you are not familiar with the package, you might want to consult the data.table [FAQ available on CRAN] (http://cran.r-project.org/web/packages/data.table/vignettes/datatable-faq.pdf).


SCRIPT ORGANIZATION
------

The scripts are contained in `./CODE`. 

The most important scripts are `00_Startup.R` which installs R dependencies and  `30_glmnet_model.R`, which contains our current risk model. 

The other scripts download and prepare the data. These data are already in the `./DATA` directory, so you should not need to run thes scripts.

DATA
------

Data used to develop the model is stored in the ``./DATA`` directory. [Chicago’s Open Data Portal](http://data.cityofchicago.org). The following datasets were used in the building the analysis-ready dataset. 

```
Business Licenses
Food Inspections 
Crime
Garbage Cart Complaints
Sanitation Complaints
Weather
Sanitarian Information
```

The data sources are joined to create a tabular dataset that paints a statistical picture of a ‘business license’- The primary modelling unit / unit of observation in this project.

The data sources are joined (in SQLesque manner) on appropriate composite keys. These keys include Inspection ID, Business License, and Geography expressed as a Latitude / Longitude combination among others. 


Acknowledgements
----------------
This research was conducted by the [City of Chicago](http://www.cityofchicago.org/city/en/depts/doit.html) with support from the [Civic Consulting Alliance](http://www.ccachicago.org/), and [Allstate Insurance](https://www.allstate.com/). The City would especially like to thank Stephen Collins, Gavin Smart for their efforts in developing the predictive model. We also appreciate the help of Kelsey Burr, Christian Hines, and Kiran Pookote in coordinating this research project. We owe a special thanks to our volunteers from Allstate who put in a tremendous effort to develop the predictive model.

License
-------
Copyright, 2014 City of Chicago

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the “Software”), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

Libraries and other software utilized in this repository are copyrighted and distributed under their respective open source licenses.
