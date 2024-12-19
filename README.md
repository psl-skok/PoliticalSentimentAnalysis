<h1>Sentiment and Emotion Analysis of Political Subreddits Over Time</h1>
<b>Project by</b> Paul Skok and Patrick Leary

<h2>Overview:</h2>
In this project, we analyze the sentiment and emotion of hundreds of thousands of comments from political subreddits between 2020 and 2024. We focus on comparing the sentiment and emotions between left-leaning and right-leaning subreddits at different points in time, while discussing potential reasons for observed differences.

- <b>Write Up: [link](https://docs.google.com/document/d/15BtjCK3yZl-UmYoEFYJbWrTkN6B0iZqHVPY15rN4eZA/edit?tab=t.0)</b>
- <b>Data Source: [link](https://drive.google.com/drive/u/1/folders/1xcEhtoVrIWVByhD9XWwk0mnteDY7udsy)</b>

<h2>Project Structure:</h2>

- <b>Data Reading and Cleaning</b>
  - The datasets are read from CSV files, combined, and filtered into two main categories: left and right-leaning subreddits. Data from 'other' subreddits is excluded from the analysis. The data is also organized by necessary columns, including comment text, subreddit, time of post, and sentiment-related fields.
  
- <b>Sentiment Analysis</b>
  -  Using NLTK's built-in VADER SentimentIntensityAnalyzer, we perform sentiment analysis on each comment to obtain the following sentiment scores:
      -   Negative sentiment (comment_neg)
      -   Neutral sentiment (comment_neu)
      -   Positive sentiment (comment_pos)
      -   Compound score, which combines the previous scores into a single overall sentiment (comment_compound).

- <b>Emotion Detection</b>
  - We apply an emotion detection model to a random sample of comments from each political group (left and right) for each month. The model predicts the dominant emotion in the text, which is stored in a new DataFrame along with a score for each emotion. This model is computationally intensive, so the data is sampled, and results are saved to ensure efficiency.

- <b>Data Manipulation and Visualization</b>
  - The data is aggregated and visualized, showcasing the sentiment and emotion trends over time for both left and right-leaning subreddits. Key visualizations include:
    - Sentiment Over Time: Plots showing the sentiment trends over time (monthly and daily) for both political sides, with significant events like Biden’s election and the United States’ support for Ukraine.
    - Emotion Frequency: Visualizations of the frequency of different emotions (e.g., anger, joy, sadness) in the left and right-leaning subreddits, normalized for comparison.
    - Emotion Over Time: Plots of how emotions (excluding neutral) change over time, again divided by political side.

<h2>Installation:</h2>
To run this project, you'll need to install the necessary Python libraries. The key dependencies are:

```bash
pip install pandas numpy matplotlib nltk transformers
```

If you're working on Google Colab(recommended), you can directly mount your Google Drive to access the datasets using the following code:

```python
from google.colab import drive
drive.mount('/content/drive', force_remount=True)
```


<h2>Dataset Details:</h2>
The datasets consist of Reddit comments from political subreddits, categorized into left and right political groups. The files used in this analysis are:

  - reddit_opinion_democrats.csv: Data for left-leaning subreddits
  - reddit_opinion_republican.csv: Data for right-leaning subreddits
    
You can find these datasets in the shared Google Drive folder [here](https://drive.google.com/drive/u/1/folders/1xcEhtoVrIWVByhD9XWwk0mnteDY7udsy).

<h2>How to Use:</h2>

  - <b>Mount Google Drive:</b> Ensure your Google Drive is mounted if you're using Colab.
  - <b>Read and Clean Data:</b> Load the datasets and combine them into a single DataFrame.
  - <b>Run Sentiment Analysis:</b> Apply the VADER sentiment model to the text of the comments.
  - <b>Run Emotion Detection:</b> Apply the emotion detection model to a random sample of the comments.
  - <b>Visualize the Data:</b> Aggregate and visualize the sentiment and emotion trends over time using the provided plots.

<h2>Key Findings:</h2>

  - <b>Sentiment Over Time:</b> Graphs illustrating how sentiment fluctuates over time, with notable spikes around political events such as elections.
  - <b>Emotion Frequency:</b> A comparison of emotional responses in left and right subreddits, showing differences in emotional tone.
  - <b>Emotion Over Time:</b> Insights into how emotional responses change over time, including the exclusion of neutral emotions to focus on stronger feelings like joy or anger.
