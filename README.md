# Amazon_Vine_Analysis

## Overview of the analysis: 

The Amazon Vine program is a service provided for manufacturers/publisher.  They can choose to pay for the service in order to get reviews for their products.  Vine members would then be required to provide a review.  This analysis focuses on the bias of the Vine program. <br>

For the first part of this project, the reviews were extracted from AWS's S3 bucket, transformed and then loaded into Postgres.  The script is saved as [Amazon_Reviews_ETL.ipynb](https://github.com/taranahassan/Amazon_Vine_Analysis/blob/main/Amazon_Reviews_ETL.ipynb)

## Results: 

In order for the analysis to be more effective, initially the dataset has been filtered before creating a DataFrame.  Any votes under 20 for the total votes column, was removed to avoid division by zero errors later on. <br>
The Vine table was further filtered to identify the percentage of helpful votes vs. the total vote equal or greater than 50%.
<br>
![df](https://user-images.githubusercontent.com/75437852/114807748-f3623980-9d74-11eb-8ea2-90813bee76c5.PNG)

Using the filtered DataFrame above, we are able to establish a total number of reviews of 107421.  Out of those total votes:

  1.  There are 1223 Vine reviews and 106198 non-Vine reviews<br>
  ![paid_reviews](https://user-images.githubusercontent.com/75437852/114811068-68387200-9d7b-11eb-9df3-914f6aaa9012.PNG)![unpaid_reviews](https://user-images.githubusercontent.com/75437852/114811079-6f5f8000-9d7b-11eb-9331-bc8622d0b198.PNG)
<br>
  2.  About 41% of all Vine reviews received 5 star ratings, which is 510 reviews part of the Vine program <br>
  ![vine_star_rating](https://user-images.githubusercontent.com/75437852/114890865-656c6a00-9dd9-11eb-8a72-a36508140bfe.PNG)![paid_percentage](https://user-images.githubusercontent.com/75437852/114890948-75844980-9dd9-11eb-8703-8981e206c667.PNG)
<br>
  3.  Approximately 43% of all non Vine reviews received 5 star ratings which is a total of 46549 reviews <br>
  ![nonvine_star_rating](https://user-images.githubusercontent.com/75437852/114893270-8c2ba000-9ddb-11eb-84b9-8e342cdb0804.PNG)![unpaid_percentage](https://user-images.githubusercontent.com/75437852/114893346-99488f00-9ddb-11eb-93e7-b0325cee89f4.PNG)
<br>

***The DataFrames of this analysis are saved on [Vine_Review_Analysis.ipynb](https://github.com/taranahassan/Amazon_Vine_Analysis/blob/main/Vine_Review_Analysis.ipynb).*** <br>

# Summary: 
In your summary, state if there is any positivity bias for reviews in the Vine program. Use the results of your analysis to support your statement. Then, provide one additional analysis that you could do with the dataset to support your statement.
