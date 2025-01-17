This repository contains the, a powerful tool to monitor Twitter sentiment for cryptocurrency tokens using `twikit` and `HuggingFace` models. It provides real-time sentiment analysis and stores sentiment history.

---

## **How It Works**

### **Core Functionality**
1. **Twitter Sentiment Analysis**: 
   - Monitors Twitter mentions for tokens like `solana`, `bitcoin`, and `ethereum`.
   - Uses HuggingFace models to analyze sentiment (positive, neutral, negative).
   - Tracks sentiment changes over time.

2. **Sentiment Announcement**:
   - Announces significant sentiment changes using text-to-speech (OpenAI voice models).

3. **Data Storage**:
   - Stores sentiment history and tweet data for long-term tracking.

---

## **Setup Instructions**

### **Pre-requisites**
1. **Python Environment**:
   - Ensure you have Python 3.8 or higher installed.

2. **Dependencies**:
   - Install required Python libraries by running:
     ```bash
     pip install -r requirements.txt
     ```

3. **Environment Variables**:
   - Add your credentials in a `.env` file:
     ```env
     TWITTER_API_KEY=your_api_key
     TWITTER_API_SECRET=your_api_secret
     OPENAI_KEY=your_openai_key
     ```
   - Refer to `.env.example` for an example setup.

4. **Generate Twitter Cookies**:
   - Run the Twitter login script to generate `cookies.json`:
     ```bash
     python src/scripts/twitter_login.py
     ```
   - This file will be used for authenticated API requests.

---

## **How to Run**

1. **Initialize Sentiment Agent**:
   - Start the sentiment agent by running:
     ```bash
     python src/main.py
     ```

2. **Configure Tokens to Track**:
   - Edit the `TOKENS_TO_TRACK` list in the configuration section of `main.py` to include your desired tokens:
     ```python
     TOKENS_TO_TRACK = ["solana", "bitcoin", "ethereum"]
     ```

3. **Set Run Interval**:
   - Configure how frequently sentiment checks occur by updating `CHECK_INTERVAL_MINUTES`:
     ```python
     CHECK_INTERVAL_MINUTES = 15
     ```

4. **Monitor Output**:
   - Sentiment results will be printed in the console and significant changes will trigger text-to-speech announcements.

---

## **Logic and Workflow**

### **Initialization**
1. Load environment variables (`.env`) and cookies (`cookies.json`).
2. Initialize sentiment analysis model (HuggingFace's `bertweet-base-sentiment-analysis`).
3. Create necessary directories (e.g., `src/data/sentiment`).

### **Tweet Collection**
1. Search Twitter for mentions of specified tokens.
2. Exclude irrelevant tweets based on keywords in `IGNORE_LIST`.
3. Save tweets to CSV, avoiding duplicates.

### **Sentiment Analysis**
1. Use the BERT model to analyze sentiment scores for collected tweets.
2. Convert scores to a scale from -1 to 1.
3. Save sentiment scores to a history file (`sentiment_history.csv`).

### **Announce Results**
1. Calculate sentiment changes since the last run.
2. Announce significant changes using OpenAI's text-to-speech API.
3. Print detailed results to the console.

---

## **Configuration Options**

### **Sentiment Settings**
- **Threshold for Announcement**:
  - Announce sentiment changes if the absolute sentiment score exceeds:
    ```python
    SENTIMENT_ANNOUNCE_THRESHOLD = 0.4
    ```

### **Voice Settings**
- Configure voice settings for announcements:
  ```python
  VOICE_MODEL = "tts-1"   # Options: tts-1, tts-1-hd
  VOICE_NAME = "nova"     # Options: alloy, echo, fable, onyx, nova, shimmer
  VOICE_SPEED = 1          # Speed range: 0.25 to 4.0
  ```

---

## **Files and Directories**
```
.
├── src/
│   ├── main.py                     # Main entry point for the sentiment agent
│   ├── agents/
│   │   └── trading_agent.py        # Sentiment analysis logic
│   ├── data/
│   │   ├── sentiment/              # Sentiment data storage
│   │   └── sentiment_history.csv   # Sentiment history file
│   ├── scripts/
│   │   └── twitter_login.py        # Script to generate cookies.json
│   └── nice_funcs.py               # Utility functions
├── requirements.txt                # Python dependencies
├── .env                            # Environment variables (not included in repo)
└── .env.example                    # Example environment variables file
```

---

## **Future Improvements**
1. Add support for tracking multiple social media platforms.
2. Implement a web dashboard for real-time sentiment tracking.
3. Enhance sentiment analysis with more advanced NLP models.

---

## **License**
This project is licensed under the MIT License. See `LICENSE` for more details.
