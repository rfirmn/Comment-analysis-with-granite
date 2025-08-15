
# TikTok Comment Analysis with Granite AI

This project provides an end-to-end pipeline to **scrape, translate, analyze, and visualize TikTok comments** using the [IBM Granite 3.2-8B Instruct model](https://replicate.com/ibm-granite/granite-3.2-8b-instruct) via the Replicate API.

## Features
- **Scrape TikTok comments** from a given post URL.
- **Translate non-English comments** to English for better AI model performance.
- **Sentiment analysis**: Classify comments as Positive, Negative, Neutral, or Mixed.
- **Emotion classification**: Detect emotions such as Happy, Sad, Angry, etc.
- **Visualizations**:
  - Sentiment distribution pie chart
  - Emotion distribution pie chart
  - Word Cloud of frequently used words
- **Automated summary generation** of insights.

## Requirements
- Python 3.8+
- Google Colab (recommended for seamless API token management)
- Replicate API token
- TikTok post URL

## Installation

Run the following commands to install dependencies:

```bash
!pip install langchain_community
!pip install replicate
!pip install wordcloud
!pip install matplotlib pandas requests
```

## Setup

1. **Get a Replicate API Token**  
   Sign up at [Replicate](https://replicate.com/) and generate your API token.

2. **Store API Token in Google Colab**  
   ```python
   from google.colab import userdata
   api_token = userdata.get('api_token')
   ```

3. **Set Model Parameters**  
   ```python
   from langchain_community.llms import Replicate
   import os

   os.environ["REPLICATE_API_TOKEN"] = api_token
   model = "ibm-granite/granite-3.2-8b-instruct"
   output = Replicate(model=model, replicate_api_token=api_token)
   ```

## Usage

### 1. Scrape TikTok Comments
```python
post_url = 'https://www.tiktok.com/@username/video/VIDEO_ID'
# Extract post_id and request comments from TikTok's endpoint
```

*Note*: If you don't want to scrape, you can directly load the prepared CSV from the [GitHub repository](https://github.com/rfirmn/Comment-analysis-with-granite.git).

### 2. Load Dataset
```python
import pandas as pd
df = pd.read_csv("TikTok Comments.csv")
```

### 3. Translate Comments to English
```python
# Batch processing to avoid API limits
def translate_batch(comments):
    # Call Granite AI to translate
    pass
```

### 4. Sentiment & Emotion Analysis
```python
# Call Granite AI with classification prompts
```

### 5. Visualize Results
```python
import matplotlib.pyplot as plt
from wordcloud import WordCloud

# Pie chart sentiment
# Pie chart emotion
# WordCloud
```

### 6. Generate Summary
```python
# Prompt Granite AI to summarize insights
```

## Example Output

**Sentiment Pie Chart**  
_Positive, Negative, Neutral, Mixed_ distribution of comments.

**Emotion Pie Chart**  
_Distribution of emotions detected from comments._

**Word Cloud**  
_Visual representation of most frequent words._

**Summary Example**  
```
Overall sentiment towards the TikTok video is overwhelmingly positive, with high engagement and expressions of joy...
```

## Notes
- API token must be kept secure.
- TikTok scraping may fail if API endpoints change or rate limits are reached.
- Translation step is crucial for non-English datasets.
- Batch size should be tuned to avoid API timeouts.

## License
This project is for educational purposes only.
