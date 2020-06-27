# analyse-and-wrangle-WeRateDogs-data

## Introduction

This project focused on wrangling data from the WeRateDogs Twitter account using Python, documented in a Jupyter Notebook (wrangle_act.ipynb). This Twitter account rates dogs with humorous commentary. The rating denominator is usually 10, however, the numerators are usually greater than 10.  The numerators, however? Almost always higher than 10. 11/10, 12/10, 13/10, etc. Why? Because "they're good dogs, Brent." WeRateDogs has over 4 million followers and has received international media coverage. 

## Project Details

    Data wrangling, which consists of:
       Gathering data
       Assessing data
       Cleaning data

    Storing, analyzing, and visualizing your wrangled data

    Reporting on 1) Data wrangling efforts and 2) Data analyses and visualizations

The goal of this project is to wrangle the WeRateDogs Twitter data to create interesting and trustworthy analyses and visualizations. The challenge lies in the fact that the Twitter archive is great, but it only contains very basic tweet information that comes in JSON format. I needed to gather, assess and clean the Twitter data for a worthy analysis and visualization.

## What are the input and output files of the project?

    Inputfiles: see url's in Origin of data sources section above:
    - `twitter_archive_enhanced.csv` file with basic data of the WeRateDogs tweeets
    - `image_predictons.tsv` file with dog breed predictions of neural network
 
    Work files:
    * `wrangle_act v1.2_DIRK.ipynb` : this is the extensive notebook with all details about the data gathering, wrangling and cleaning
    * output file with the wrangled data of this data wrangling/cleaning exercise of the former bullit:
        - twitter_overal_table pandas dataframe saved in the `twitter_archive_master.csv` file
        - twitter_overal_table pandas dataframe is also saved in the `bestofrt.db database` file
  
    And the 2 report files:
    * the `wrangle_report_DIRK_KADIJK_v1.1.ipynb` file of this report which describes the wrangling/cleaning efforts and outputs
    * the `act_report_DIRK_KADIJK_v1.1.ipynb` file which communicates the insights and visualizations produced from the wrangled data

## Origin of Data sources

We gather 3 pieces of data:

### a. Enhanced Twitter Archive

The WeRateDogs Twitter archive contains basic tweet data for all 5000+ of their tweets, but not everything. One column the archive does contain though: each tweet's text, which I used to extract rating, dog name, and dog "stage" (i.e. doggo, floofer, pupper, and puppo) to make this Twitter archive "enhanced.". We manually downloaded this twitter_archive_enhanced.csv file by clicking the following [link](https://d17h27t6h515a5.cloudfront.net/topher/2017/August/59a4e958_twitter-archive-enhanced/twitter-archive-enhanced.csv). 

### b. Image Predictions File

The tweet image predictions, i.e., what breed of dog (or other object, animal, etc.) is present in each tweet according to a neural network. This file (image_predictions.tsv) hosted on Udacity's servers and we downloaded it programmatically using python Requests library AND the following URL of the file: https://d17h27t6h515a5.cloudfront.net/topher/2017/August/599fd2ad_image-predictions/image-predictions.tsv)

### c. Twitter API

Back to the basic-ness of Twitter archives: retweet count and favorite count are two of the notable column omissions. Fortunately, this additional data can be gathered by anyone from Twitter's API. Well, "anyone" who has access to data for the 3000 most recent tweets, at least. But we, because we have the WeRateDogs Twitter archive and specifically the tweet IDs within it, can gather this data for all 5000+.
In this project, I'll be using Tweepy to query Twitter's API for data included in the WeRateDogs Twitter archive. This data will include retweet count and favorite count.

## Research Questions

This investigation of WeRateDogs data is focused on the following 3 research questions:
* Research Question #1: To what extend is there a possitive correlation between a high rating_numerator at the one end, and a higher favorite_count (or retweet_count) at the other hand.

* Research Question #2: Does filtering out of the "non-dog" predictions and the #1 predictions with probability <70% improve the correlation between rating_numerator and retweet_count / favorite_count? 

* Research Question #3: Which dograces (dog breeds) are top performing in terms of rating_numerator ?¶ 





