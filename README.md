# EthioMart Data Extraction & Labeling

EthioMart focuses on extracting and labeling data from Ethiopian Telegram e-commerce channels to support Named Entity Recognition (NER) tasks. The primary objective is to identify and label entities such as **products**, **prices**, and **locations** from Amharic text within messages, enabling seamless integration with machine learning models.

---

## **Project Overview**

The workflow is structured into the following key steps:

### **1. Data Collection**
Scrape data from Ethiopian Telegram e-commerce channels using a custom-built Telegram scraper.

### **2. Data Preprocessing**
Clean and format the scraped data:
- Filter messages containing Amharic text.
- Tokenize and normalize the content for consistency.

### **3. Entity Labeling**
Manually label a subset of messages to identify and categorize entities using the CoNLL format:
- **B-PRODUCT**: Beginning of a product entity.
- **I-PRODUCT**: Inside a product entity.
- **B-LOC**: Beginning of a location entity.
- **I-LOC**: Inside a location entity.
- **B-PRICE**: Beginning of a price entity.
- **I-PRICE**: Inside a price entity.
- **O**: Tokens that do not belong to any entity.

### **4. Output**
Save the labeled data in the CoNLL format for future use in machine learning models.

---

## **Prerequisites**

Ensure you have **Python 3.7 or higher** installed.

### Required Libraries:
- **telethon**: For Telegram scraping
- **pandas**: For data manipulation
- **re**: For handling regular expressions
- **dotenv**: For loading environment variables
- **asyncio**: For managing asynchronous operations

Install the required libraries using:
```bash
pip install -r requirements.txt
```

---

## **Setup**

1. **Create a `.env` file**: Add your Telegram API credentials. Obtain these credentials by creating a bot via BotFather.

   Example `.env` file:
   ```
   TG_API_ID=your_api_id
   TG_API_HASH=your_api_hash
   PHONE=your_phone_number
   ```

2. **Run the Telegram Scraper**: Use the scraper to collect data from selected Telegram channels:
   ```bash
   python scrape_telegram_data.py
   ```

3. **Data Preprocessing**: Prepare the scraped data by filtering Amharic messages and tokenizing the text. This step ensures the data is clean and ready for labeling.

4. **Entity Labeling**: Manually annotate entities in a subset of the dataset following the CoNLL format. Store the labeled entities in a plain text file:
   - **File Name**: `labeled_telegram_product_price_location.txt`

---

## **Files Overview**

- **`scrape_telegram_data.py`**: Script for scraping data from Telegram channels.
- **`preprocess_data.py`**: Preprocessing script for cleaning, filtering Amharic text, and tokenizing messages.
- **`labeled_telegram_product_price_location.txt`**: Contains labeled data in the CoNLL format.
- **`requirements.txt`**: List of required Python libraries.

---
### **Sample Entity Labels in CoNLL Format**
```plaintext
አንድ B-PRODUCT
በር O
ብር B-PRICE
እና O
አዲስ B-LOC
አበባ I-LOC
```
This structured format ensures clarity for training machine learning models to recognize and extract relevant entities from Amharic e-commerce data.

## **Contact**
For more information or inquiries about EthioMart, feel free to reach out via the project repository or the contact details provided.