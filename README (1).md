# PakWheels YouTube Content Detective

**Question:** Which content types get Pakistani audiences to engage?
Sentiment and engagement analysis of 2,836 public PakWheels YouTube comments (173 videos).

## Files
- `notebook.ipynb`: full code (scraping, cleaning, sentiment, analysis, recommendations)
- `pw_final.csv`: cleaned comments with sentiment and content type
- `pw_chart1.png`: average engagement by sentiment
- `pw_chart2.png`: average engagement by content type
- `pw_chart3.png`: sentiment by content type
- `recommendations.txt`: recommendation engine output

## Method
1. YouTube Data API v3: 300 most recent videos, up to 40 top comments each.
2. Cleaning: removed duplicates and empty comments. Engagement = likes + replies.
3. Sentiment: `cardiffnlp/twitter-xlm-roberta-base-sentiment` (80% agreement on 50 manually checked comments).
4. Content types: rule-based keyword grouping of video titles into six types.
5. Robust metrics: mean, share of comments with a like/reply, and mean with the top 5% viral comments capped.

## Key findings
- 39% negative, 35% neutral, 26% positive comments.
- Positive comments get about 2x the engagement of negative ones (1.14 vs 0.53, capped).
- Owner reviews do best; expert/first-look reviews do worst (about 2x gap).
- News/price posts attract the most negative comments (45%).

## Run it yourself
Open the notebook in Google Colab, add your own YouTube API key in the first cell, and run all cells. The API key is not included in this repository.

## Limitations
Top 40 comments per video (not a random sample), small manual check by one person, keyword-based content types, video age not controlled, association not causation.
