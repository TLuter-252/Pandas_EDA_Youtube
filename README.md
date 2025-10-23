# 🇺🇸 US YouTube Trending Statistics 🇺🇸

## Goal of the Project:

We are looking at Trending YouTube Video Statistics and analyzing metadata that pertains to the videos' viewer engagement.
We want to map out the relationship between the different metadata and see if there are any correlations.

## Possible Benefits:

Our findings can either help reinforce or go against the popular notion that video engagement are related.

## Describe the Data:
### Columns:

We kept the data columns that were most relevant to a video's viewer engagement.

We removed the following columns as we determined that they were not directly relevant to viewer engagement: `video_id`, `trending_date`, `title`, `channel_title`,`category_id`, `publish_time`, `tags`, `thumbnail_link`, `description`, `comments_disabled`,`ratings_disabled`, and `video_error_or_removed`. Category Id would be more useful if we wanted to isolate what kinds of videos were trending, but we wanted to look at overall trending data, and it was given.

We kept data columns for `views`, `likes`, `dislikes`, and `comment_count` as quantitive measures for video's viewer engagement.

### Features:

The `views` column contains the amount of views that a trending video received from all web traffic.

The `likes` column contains the amount of likes that a trending video received from logged-in YouTube accounts.

The `dislikes` column contains the amount of dislikes that a trending video received from logged-in Youtube accounts.

The `comment_count` column contains the amount of comments that a trending video received from logged-in YouTube accounts.

### Numerical/Categorical/Text?

filler


### Data missing, handling?

The `description` had 40379 entries filled out of 40949 total entries. This means that some videos were lacking a description.

We removed this column entirely because we did not need it for our analysis, as the information there would not add to our goal.

Every other column had a value inside, all of them being qualitative data such as `video_id` and `tags` that would not be useful for our analysis.

### Related Features, Values?

filler

### Plots

filler