# Viewer Engagement Metrics in Trending YouTube Videos

## Goal of the Project:

We looked at the data set for Trending YouTube Video Statistics for the US from 2017 to 2018 and analyzed metadata that pertains to the videos' viewer engagement.

We wanted to map out the relationship between the different viewer engagement metrics and see if there were any correlations.

## Possible Benefits:

Our findings could either help reinforce or contradict the popular notion that the various metrics for video engagement are related, and possibly reveal relationship that we have not seen before.

## Describe the Data:
### Columns:

We removed the following columns as we determined that they were not directly relevant to viewer engagement:
- `video_id`: unique identifier for video in hyperlink
- `trending_date`: date time of when video was trending
- `title`: title of video
- `category_id`: numerical identifier for video's category
- `publish_time`: when video was uploaded
- `tags`: phrases used to promote video in search results
- `thumbnail_link`: hyperlink to thumbnail picture
- `description`: video's description text
- `comments_disabled`: boolean of comments enabled or disabled
- `ratings_disabled`: boolean of ratings enabled or disabled
- `video_error_or_removed`: boolean of video error and removed

These columns were largely qualitative labels that uniquely identified each video, which would not be helpful for us; we wanted raw quantitative data regardless of video title, channel uploader, category and content.

We kept columns for:
- `views`: how many times the trending video was viewed
- `likes`: how many logged-in users liked the video
- `dislikes`: how many logged-in users disliked the video
- `comment_count`: how many logged-in users left comments
- `channel_title`: channel or uploader name

as they pertained directly as measures for video's viewer engagement.

### Features:

We found that as `views` went up, `likes` increased the most, followed by `comment_count` then `dislikes` in that specific order.

We also found that a viewer enjoying a video will be likely to increase a video's `views`, `likes` and `comment_count`; conversely, a viewer not enjoying a video will likely increase the video's `dislikes` and `comment_count`.


### Numerical/Categorical/Text?

We dealt purely with numerical data that could be compared with one another. Most of the columns were qualitative text-based data.

We were initially interested in `category_id` discarded categorical data because it was an ordinal number that didn't actually provide us categories.

We were also initially interested in `publish_time` and `trending_date` as they could possibly reveal patterns, but the provided dataset already was already a snippet of trending video data from a range of about a year from 2017 to 2018, so they were  not be particularly useful for drawing conclusions.


### Data missing, handling?

The `description` had 40379 entries filled out of 40949 total entries. This means that some videos were lacking a description.

We removed this column entirely because we did not need it for our analysis, as the information there would not add to our goal.

Every other column had a value inside, including the three boolean columns `comments_disabled`, `ratings_disabled` and `video_err_or_removed` that had a boolean value.

### Related Features, Values?

Although not provided in the US Trending YouTube Video Statistics, if there was monetary data such as revenue from ads or from affiliate links, sponsors, etc. we could draw more direct conclusions.

### Plots

We made several plots to try to map out the relationship between the viewer metrics.

#### A. Tim's Plots Here
Graph 1: Likes and Dislikes per Top 20 Videos

What it shows: The 20 most-viewed videos. For each video, you see likes (green bars going up) and dislikes (red bars going down).
X-axis: The video’s view count (bigger number = further to the right).
Y-axis: The size of the bar = how many likes or dislikes that video has.
Why some bars go down: Dislikes are plotted as negative so you can see likes vs. dislikes for the same video without stacking on top of each other.

How to read it: Taller green bars mean a video got a lot of likes; deeper red bars mean a lot of dislikes. Compare the two bars around the same x-position to see the “approval vs. disapproval” for that video.

Graph 2 (H Bar) : Top 20 Channels by Likes per View

What it shows: The channels that get the highest like rate overall.
Like rate = total likes ÷ total views for each channel (so bigger channels don’t win just because they have more views).

How to read it: Longer bars = a higher share of viewers clicked “like.”. It only includes channels with at least 3 videos and at least 1,000,000 total views, so tiny channels don’t skew the results.

Graph 3 (H Bar): Top 20 Channels by Comments per View

What it shows: The channels that spark the most comments per view.
Comment rate = total comments ÷ total views (again, adjusted for size).
Same filters as above (≥3 videos and ≥1,000,000 views).

How to read it: Longer bars = viewers are more likely to leave a comment when they watch that channel’s videos.


#### B. Scatter Plot

We made a scatter plot mapping `views` measured against `likes`, `dislikes`, and `comment_count` to show that as views increased, all three of those other metrics increased. we used millions as units in this scatter plot since those were the most human-readable units and were provided in the dataset.

This revealed to us the order in which the metrics increased as views increased: `likes` first, followed by `comment_count`, then by `dislikes`. So viewers were most likely to `like` a video when they watched one, then `comment` on it more so than / before `dislike`ing it.

#### C. Correlation Heatmap

Lastly we created a correlation heatmap to show the specific relationships between all four metrics.

We found the positive correlations between the metrics:
- Strongest between `views` and `likes` at `0.85`
- Followed by `likes` and `comment_count` at `0.8`
- Then by `dislikes` and `comment_count` at `0.7`
- Then by `views` and `comment_count` at `0.62`
- Then by `views` and `dislikes` at `0.47`
- Then by `likes` and `dislikes` at `0.45`

As stated above, this showed us that certain metrics were more likely to be paired with others.
