# Amazon_Vine_Analysis

## Overview of the analysis: 

The Amazon Vine program is a service provided for manufacturers/publishers.  They can choose to pay for the service in order to get reviews for their products.  Vine members would then be required to provide a review.  This analysis focuses on the bias of the Vine program. <br>

*For the first part of this project, the reviews were extracted from AWS's S3 bucket, transformed and then loaded into Postgres.  The script is saved as [Amazon_Reviews_ETL.ipynb](https://github.com/taranahassan/Amazon_Vine_Analysis/blob/main/Amazon_Reviews_ETL.ipynb)*

## Results: 

In order for the analysis to be more effective, initially the dataset has been filtered before creating a DataFrame.  Any votes under 20 for the total votes column, was removed to avoid division by zero errors later on. <br>
The Vine table was further filtered to identify the percentage of helpful votes vs. the total vote equal or greater than 50%.
<br>

Using the filtered DataFrame we are able to establish a total number of reviews of **99,046**.  Out of those total votes:

  1.  There are **1,207** Vine reviews and **97,839** non-Vine reviews<br>
  
![paid_reviews](https://user-images.githubusercontent.com/75437852/114918412-0d436100-9df5-11eb-8ddf-9e059482b5d3.PNG)
<br>
![unpaid_reviews](https://user-images.githubusercontent.com/75437852/114918447-159b9c00-9df5-11eb-9bc0-c25ef542bb1d.PNG)
<br>
<br>
  2.  About **41%** of all Vine reviews received 5 star ratings, which is **509** reviews part of the Vine program <br>
   
![paid_percentage](https://user-images.githubusercontent.com/75437852/114918662-5398c000-9df5-11eb-8041-dcb40eb16aee.PNG)
<br>
![vine_star_rating](https://user-images.githubusercontent.com/75437852/114918701-627f7280-9df5-11eb-8649-df8d87e782c1.PNG)
<br>
<br>
  3.  Approximately **46%** of all non Vine reviews received 5 star ratings which is a total of **45,858** reviews <br>
  
 ![unpaid_percentage](https://user-images.githubusercontent.com/75437852/114918794-82169b00-9df5-11eb-8dc9-4e022cfc8e41.PNG)<br>
![unpaid_reviews](https://user-images.githubusercontent.com/75437852/114918807-85aa2200-9df5-11eb-936a-fafbbf8767ad.PNG)
<br>
<br>
***The DataFrames of this analysis are saved on [Vine_Review_Analysis.ipynb](https://github.com/taranahassan/Amazon_Vine_Analysis/blob/main/Vine_Review_Analysis.ipynb).*** <br>

# Summary: 

Based on the results, there seems to be no positivity bias for the Vine program at all.  
<br>
The overall number of reviews in this dataset (after filtering) is 99,046.
<br>
<br>
![total_reviews](https://user-images.githubusercontent.com/75437852/114918923-a5d9e100-9df5-11eb-84ac-b58a018217c9.PNG)
<br>
<br>
And the total 5 star ratings out of all the reviews are **46,367**. 
<br>
<br>
![star_ratings](https://user-images.githubusercontent.com/75437852/114919223-f8b39880-9df5-11eb-93c5-033951669557.PNG) <br>
<br>
When comparing the difference of numbers between Vine reviews and non-Vine reviews, there is **98%** more reviews that are not part of the Vine program.  The 5 star reviews within the Vine program is also sufficiently low, below **50%**; which indicates a negative bias towards the Vine program.  Even though non-Vine program's star rating is still not at 50%, it is still higher by about 4 points compared to star ratings part of the Vine program.<br>

To further the analysis and shed light on more facts, to have a more definitive answer if any bias for the Vine program exists, the vine table can be filtered by the "verified_purchase" column. We can extract all the reviews based on products that were actually purchased. <br>
Below is an example of the table filtered and the code following for results: 
<br>
<br>
![verified_purchase](https://user-images.githubusercontent.com/75437852/114971915-60e09980-9e4b-11eb-94d0-a2fd68211e8f.PNG)
<br>
<br>
![revised_analysis](https://user-images.githubusercontent.com/75437852/114971589-a18be300-9e4a-11eb-9d24-f7c28d25d4d6.PNG)
<br>
<br>
As per the image above; the total count for reviews that were a "verified_purchase", is **54,835**.  Within that total, about 48% of the reviews were rated with 5 stars.  Further in the results, it shows that only **9** reviews part of the Vine program received 5 stars and that actually have purchased the product.  Again, this indicates no positive bias for the Vine program, in return it only indicates that 5 star reviews on products can be received without purchased the Vine services.
