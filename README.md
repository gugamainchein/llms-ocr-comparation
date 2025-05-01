# PDF Document Text Extraction using Amazon Bedrock

This project demonstrates how to extract and compare text from PDF documents using two powerful image-capable Large Language Models (LLMs) available through Amazon Bedrock:

- **Claude 3.7 Sonnet** by Anthropic
- **Amazon Nova Pro** by Amazon

Each page of a PDF is converted into an image and sent to both models in parallel to extract textual information. The results are saved as `.txt` files per page for further analysis or use.

---

## 📁 Project Structure

```
├── documents.ipynb   # Original notebook
├── documents/        # Folder where input PDF files are stored
├── images/           # Folder where images of PDF are stored
├── texts/            # Folder where extracted text results are saved
└── README.md         # This file
```

---

## 🔧 How It Works

### Step 1: Convert PDF Pages to Images

Using the `fitz` library, the notebook converts each page of a PDF into high-quality PNG images.

### Step 2: Define LLM Extractor Functions

Two asynchronous Python functions are defined to:

- Encode the image in base64
- Send it to each model via `boto3` and the Amazon Bedrock API
- Parse and return the extracted text response

### Step 3: Parallel Processing

Using `asyncio.gather`, the notebook sends the same image to both models concurrently for faster processing.

### Step 4: Save Results

The extracted text is saved as `.txt` files per page with side-by-side comparisons of both models.

---

## 📊 LLM Metrics Tracked

For each model, the following metrics are logged and printed:

Claude 3.7 Sonnet:

- **Input Tokens**: 1666
- **Output Tokens**: 1036
- **Start Time**: 1746124263.978323
- **End Time**: 1746124292.999416

Amazon Nova Pro:

- **Input Tokens**: 2223
- **Output Tokens**: 971
- **Start Time**: 1746124263.98382
- **End Time**: 1746124279.478841

---

## 📦 Requirements

- Python 3.11+
- AWS credentials with access to Amazon Bedrock
- Dependencies:
  ```bash
  pip install boto3 pymupdf
  ```

---

## 🚀 How to Run

1. Upload a PDF to the `documents/` folder.
2. Open and run the `documents.ipynb` notebook.
3. Extracted text files will be saved in the `texts/` folder.

---

## 🤝 Contributing

Feel free to fork this repo and improve model selection, add post-processing like IdP comparison, or integrate evaluation metrics like BLEU or ROUGE scores.

---

## 🧠 Author

Gustavo Mainchein — Development Specialist in AI Solutions

[LinkedIn](https://www.linkedin.com/in/gustavomainchein)

---

## 📜 License

This project is licensed under the MIT License.
