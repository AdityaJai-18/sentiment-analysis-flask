Sentiment Analysis Dashboard
A lightweight Flask web application that performs sentiment analysis on user feedback. It supports both manual text entry and batch processing via CSV file uploads, providing visual insights into sentiment distribution and key themes.

Features
Dual Input Modes: Analyze a single snippet of text or upload a CSV file for bulk analysis.
VADER Sentiment Analysis: Utilizes the NLTK VADER lexicon to calculate scores and categorize feedback as Positive, Neutral, or Negative.
Text Preprocessing: Automatically cleans data by removing URLs, special characters, and common stopwords.
Data Visualization: Generates metrics including sentiment percentage breakdown, average sentiment scores, and top frequency word analysis.
Tabular Results: Displays processed data in a clean format for easy review.

Project Structure
app.py: Main Flask application containing the NLP logic and routes.
templates/: Folder containing the HTML interface (index.html and result.html).
NLTK Data: The app automatically downloads necessary lexicons (vader_lexicon, punkt, stopwords) on the first run.
Data Input Requirements
For batch processing, the application requires a CSV file with a column explicitly named feedback.

Technical Logic
Preprocessing: Text is converted to lowercase, URLs are stripped, and NLTK stopwords are filtered out to isolate meaningful tokens.
Sentiment Scoring: The VADER engine calculates a Compound Score for each entry:
Positive: >= 0.05
Neutral: > -0.05 and < 0.05
Negative: <= -0.05
Word Frequency: The application identifies the top 12 most common words across the dataset to highlight recurring themes.
