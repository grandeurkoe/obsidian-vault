# Preliminary Exploration: The Highest Ratings, Most Reviews, and Largest Size

**Challenge**: Identify which apps are the highest rated. What problem might you encounter if you rely exclusively on ratings alone to determine the quality of an app?

**Challenge**: What's the size in megabytes (MB) of the largest Android apps in the Google Play Store. Based on the data, do you think there could be a limit in place or can developers make apps as large as they please?

**Challenge**: Which apps have the highest number of reviews? Are there any paid apps among the top 50?

## Preliminary Data Exploration

This challenge should have been fairly straightforward if you remembered to use the .sort_values() function.

`1. df_apps_clean.sort_values('Rating', ascending=False).head()`

![[2020-10-10_11-53-34-1d863b2b858ea3ad7e526a9651cf7d55.png|500]]

Only apps with very few reviews (and a low number on installs) have perfect 5 star ratings (most likely by friends and family).

`1. df_apps_clean.sort_values('Size_MBs', ascending=False).head()`

![[2020-10-10_11-53-57-9721337e76ececb8d5b1d45da3fd250f.png|500]]

Here we can clearly see that there seems to be an upper bound of 100 MB for the size of an app. A quick google search would also have revealed that this limit is imposed by the Google Play Store itself. It’s interesting to see that a number of apps actually hit that limit exactly.