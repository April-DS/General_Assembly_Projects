Files:

- [psy_astro.csv](https://raw.githubusercontent.com/April-DS/General_Assembly_Projects/master/project_3_Reddit/data/psy_astro.csv) - Scraped data from [reddit.com](https://www.reddit.com/) subredditsL psychology, astrology
- [clean_subreddits.csv](https://raw.githubusercontent.com/April-DS/General_Assembly_Projects/master/project_3_Reddit/data/clean_subreddits.csv) - Cleaned dataset with dropped duplicates


## Data Dictionary

| Feature name | Type           | Description                                |
| :----------- | :------------- | :----------------------------------------- |
| text         | str            | Title + self text of post                  |
| num_comments | int            | Number of comments under a post            |
| ups          | int            | Number of ups of post                      |
| date         | datetime64[ns] | Date of publication of post                |
| subreddit    | str            | Name of subreddit (Psychology / Astrology) |
