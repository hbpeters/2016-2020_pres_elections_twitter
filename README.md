# Introduction
The 2020 presidential election in the United States was polarizing for the American people, perhaps even historically so, as Americans grappled with casting their votes for Joe Biden or President Donald Trump in light of major events that took place in 2020, including the onset of the COVID-19 pandemic at the beginning of the year and the racial protests and riots sparked by the murder of George Floyd at the hands of the police in May. Happenings such as these have led the American people to regard the year 2020 as generally negative—it was common to hear statements in the media and amongst peers such as “2020 is the worst year ever” or “I just want 2020 to be over.” There is also talk amongst the media and general public that, politically, Americans are “more divided than ever,” largely in reference to conflicting opinions about Donald Trump’s controversial presidency. 

We are curious if there is empirical evidence of Americans’ attitudes towards politics becoming increasingly negative and polarized as suggested by these common sentiments, and how attitudes between and within political parties may have shifted in recent years. To do this, we analyze Twitter data related to the 2016 and 2020 presidential elections, specifically, as Twitter has become a popular platform for voters and candidates to express their opinions and exchange information, and the elections offer two distinct political events to measure change between. In this investigation, we develop a method of assigning political leanings to Twitter users and perform sentiment analysis and permutation testing on different groups of tweets between the two election years to assess if there are stasticially significant shifts in sentiment from 2016 to 2020, hypothesizing that tweets have become more negative and less neutral between the two years.

# The Data
We use two different datasets of tweets in this investigation, one for each election. The [2016 dataset](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/PDI7IN) was collected by researchers at Harvard and the [2020 dataset](https://github.com/echen102/us-pres-elections-2020) was collected by researchers at USC. Both groups collected tweets by tracking accounts and keywords affiliated with the elections using Twitter’s API. Each raw dataset consists of text files of tweet IDs. A tweet ID is a numerical identifier associated with a specific tweet, the full information of which is retrieved in process called “hydration” using a tool called [Twarc](https://github.com/DocNow/twarc) that is linked to Twitter’s API. Twarc returns the full information for tweets in json format, and each hydrated tweet contains data fields such as the full text of the tweet, the hashtags it uses, the users it mentions, if it was an original tweet or retweet, etc., as well as information about the Twitter user who authored the tweet.

To maintain uniformity for sentiment analysis, we filter out tweets in languages other than English. Also, the two datasets were collected by different groups that used different keyword searches to gather election-related tweets, so for our analysis to not be affected by this, we had to unify them under a universal keyword search. The keyword search used for the 2020 dataset was broader than that used for the 2016 dataset, so we filter the 2020 dataset using the 2016 keywords, changing the names of the candidates to align with the 2020 election. Our final datasets consist of 414,713 tweets from 2016 and 500,000 tweets from 2020.

# Our Approach
### Identifying the Political Left and Right

### Sentiment Analysis
The following sets of plots for each year show the distributions of compound scores for all tweets, for the left and right subsets we identified, and for the 4 types of dialogue we idenitifed. We can see that the distributions appear very similar, both between the groups for each year and across the two years. 
![2016 polarity](2016_compound_dists.png)

![2020 polarity](2020_compound_dists.png)

Similarly, the following sets of plots show how the tweets' neutrality scores are distributed.
![2016 subjectivity](2016_neu_dists.png)

![2020 subjectivity](2020_neu_dists.png)

Visually, the distributions of both the compound and neutrality scores are similar across the different groupings. We conduct permutation testing to determine if there are statistically significant differences between distributions across the two years.

### Permutation Testing

![Compound Permutation Tests](compound_permutation_tests.png)

![Neutrality Permutation Tests](neu_permutation_tests.png)

# Conclusions


# Future Work


For more details see our project's [GitHub repository](https://github.com/hbpeters/2016-2020_elections_on_twitter)   
Project site: [hbpeters.github.io/2016-2020_pres_elections_twitter](https://hbpeters.github.io/2016-2020_pres_elections_twitter)
