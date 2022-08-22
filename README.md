# We-Rate-Dogs
### by David Alobo

# Introduction

The aim of this project is to wrangle WeRateDogs Twitter data to create interesting and trustworthy analyses and visualizations. All wrangling effort was documented in a Jupyter Notebook, and showcased through analyses and visualizations using Python (and its libraries) and/or SQL.

## Overview

This project addresses the tidiness and data quality issues with the tweet data of a Twitter user, @dog_rates, of over 5000+ tweet. @dog_rates is a tweeter user with over 4 million followers and with international media coverage. @dog_rates rates people's dogs with a humorous comment about their dog.

These data are from different sources and dirty, hence, there is need to wrangle them to create interesting and trustworthy analyses and visualizations.

## Data Source

In order to achieve my goal of wrangling the 3 dataset provided from different sources and in different format, I researched the company and related my findings to the data provided. The sources and formats of these data are:

csv: The title of this file is twitter_archive_enhanced which was downloaded from the Udacity website and uploaded to the jupyter notebook. The file was read and the columns and rows were inspected. The WeRateDogs Twitter archive contains basic tweet data for all 5000+ of their tweets, but not everything. I extracted this data programmatically. The ratings probably aren't all correct. Same goes for the dog names and probably dog stages.

tsv: The title of the tsv file is image_predictions which is expected to downloaded as a .tsv file. This data is from the resulting data gathered from classification of breeds of dogs via neural network on every image in the WeRateDogs Twitter archive. This table contains full of image predictions (the top three only) alongside each tweet ID, image URL, and the image number that corresponded to the most confident prediction (numbered 1 to 4 since tweets can have up to four images).

Twitter API: This contains the omitted data - retweet count and favorite count are two of the notable column omissions. Fortunately, this additional data can be gathered by anyone from Twitter's API. Well, "anyone" who has access to data for the 3000 most recent tweets, at least. Here, I used the WeRateDogs Twitter archive and specifically the tweet IDs within it to gather this data for all 5000+ by querying Twitter's API to gather this valuable data. A developer was rquired for this to be achieved but the data was also provided by Udacity. Due the challenges of getting twitter's approval so I can finish my project on time. I downloaded the data as a json file.

## Key Findings

The 3 datasets explored in this project are:

- twitter_archive_enhanced
- image_predictions
- tweet_json
- 
The twitter_archive_enhanced datasets has a total number of 2356 rows and 17 columns. The denominator_rating which is supposed to be 10 was found out to have the following values: 10, 0, 15, 70, 7, 11, 150, 170, 20, 50, 90, 80, 40, 130, 110, 16, 120, 2. These numbers were replaced with 10.

There were no outliers present in the twitter_archive_enhanced dataset.

The image_predictions dataset has a total of 2075 rows and 12 columns. The following are the columns title of the image_predictions dataset: 'tweet_id', 'jpg_url', 'img_num', 'p1', 'p1_conf', 'p1_dog', 'p2', 'p2_conf', 'p2_dog', 'p3', 'p3_conf', 'p3_dog'. It was further discovered that 281 tweets were without images. The total number of images tweeted is 2498.

There are no duplicates record in the datasets.

## Limitations

- The approval process from twitter takes alot of time
- Incomplete data which led to the extraction and combination of data from different sources
