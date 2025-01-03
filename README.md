# Hajibrahim_X Sentiment Model

This project is a **Sentiment Analysis System** built to classify text into sentiment categories: `Positive`, `Neutral`, and `Negative`. The system uses **Hugging Face's Transformers** library with a fine-tuned BERT model for sequence classification. The project also includes a RESTful **Flask API** to serve predictions, making it suitable for real-world applications.

---

## **Features**
- **Preprocessing and Data Handling**:
  - Imported and preprocessed the Kaggle Twitter Sentiment dataset.
  - Tokenized text inputs using `BertTokenizer` for compatibility with the BERT model.
  - Encoded sentiment labels for supervised learning.

- **Model Training**:
  - Fine-tuned a pre-trained BERT model (`bert-base-uncased`) using the Hugging Face library.
  - Trained the model on the sentiment dataset for text classification tasks.

- **Flask API**:
  - Created a RESTful API endpoint to handle sentiment predictions.
  - Input: A string of text (e.g., `"I love this product!"`).
  - Output: Predicted sentiment label (`Positive`, `Neutral`, or `Negative`).

- **Error Handling**:
  - Validates incoming requests and ensures proper formatting.
  - Handles edge cases like empty input or invalid text fields gracefully.

---

## **Technical Stack**
1. **Languages**: Python
2. **Libraries**:
   - Transformers (`BertTokenizer`, `BertForSequenceClassification`)
   - Flask (for API development)
   - Torch (for model training and inference)
3. **Tools**:
   - Jupyter Notebook (development and experimentation)
   - Postman (for API testing)

---

## **Dataset**
- **Source**: [Kaggle Twitter Sentiment Analysis Dataset](https://www.kaggle.com/datasets)
- **Description**: Contains labeled tweets with sentiment categories.

---

## **API Details**

### **Endpoint**
- **URL**: `/predict`
- **Method**: POST
- **Input**: JSON object with the `text` field containing the input string.
  ```json
  {
      "text": "I love this product!"
  }
Output: JSON object with the predicted sentiment.
json
Copy code
{
    "text": "I love this product!",
    "predicted_sentiment": "Positive"
}
Project Directory
python
Copy code
Hajibrahim_X_Sentiment_Model/
│
├── sentiment_model/                 # Pre-trained model directory
│   ├── config.json                  # Model configuration file
│   ├── pytorch_model.bin            # Model weights
│   ├── tokenizer.json               # Tokenizer configuration
│   └── vocab.txt                    # Vocabulary file
│
├── app.py                           # Flask API script
├── preprocess_data.py               # Data preprocessing script
├── train_model.py                   # Model training script
├── requirements.txt                 # Dependencies
└── README.md                        # Project documentation
Setup Instructions
1. Clone the Repository
bash
Copy code
git clone https://github.com/yourusername/Hajibrahim_X_Sentiment_Model.git
cd Hajibrahim_X_Sentiment_Model
2. Install Dependencies
bash
Copy code
pip install -r requirements.txt
3. Run the Flask API
bash
Copy code
python app.py
The API will be available at http://127.0.0.1:5002/predict.
4. Test the API
Use curl or Postman:

bash
Copy code
curl -X POST http://127.0.0.1:5002/predict \
     -H "Content-Type: application/json" \
     -d '{"text": "This product is amazing!"}'
Deliverables
Trained Model: Fine-tuned BERT model stored in the sentiment_model directory.
Code Repository: Python scripts for training, preprocessing, and API deployment.
Live API: Flask API for serving predictions (can be deployed to AWS or Heroku).
Documentation: Detailed instructions for setup and usage.
Future Enhancements
Extend the model to handle multilingual data.
Deploy the API to a cloud service (AWS/Heroku) for public access.
Add a web-based front-end for user interaction.
Contact
For questions or suggestions, feel free to reach out at qayshajibrahim@gmail.com 
