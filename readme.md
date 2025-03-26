
# gaied-datadynamos-
Customer Bank Request Email Classification and Extraction
This repository provides a solution for classifying customer bank request emails and extracting relevant data using machine learning, natural language processing (NLP), and OCR (Optical Character Recognition) techniques.

Key Features:
Email Parsing: Extracts email metadata (e.g., From, To, Subject, Body, and Attachments) from .eml files.

Customer Request Classification: Classifies customer bank requests into predefined categories and subcategories using a language model (Llama 3.1).

OCR Processing for Attachments: Handles attachments in emails (PDFs or images), performing OCR to extract text content.

Data Extraction: Identifies and extracts specific attributes from email content, such as account_number, principal_amount, interest, fees, escalation, and appreciation.

Dependencies:
pandas: For data manipulation.

pydantic: For data validation.

requests: To send HTTP requests.

numpy: For numerical operations.

pytesseract: For OCR processing.

opencv-python: For image preprocessing.

pdf2image: For converting PDF pages to images (optional).

scikit-learn: For model performance evaluation.

tqdm: For progress bars.

multiprocessing: For parallel processing of large datasets.

Installation:
bash
Copy
pip install -r requirements.txt
Setup:
Email Extraction: The extract_email_data() function parses .eml files and extracts essential data, including attachments.

OCR for Attachments: PDFs and images in email attachments are processed with OCR to extract text content using pytesseract and pdf2image.

Classification and Extraction: The model classifies the email request type and extracts relevant information using Llama 3.1 API, ensuring that missing attributes return null.

Workflow:
Data Ingestion: .eml files are read, and metadata along with attachments are extracted into a pandas DataFrame.

Text Preprocessing: The email text is cleaned for UTF-8 encoding compatibility.

Request Classification: A prompt is sent to the Llama 3.1 API for classifying requests into categories and subcategories.

Attribute Extraction: Key financial attributes (e.g., account_number, fees, etc.) are extracted from email content.

Parallel Processing: The classification and extraction tasks are processed in parallel to handle large datasets efficiently.

Example Usage:
python
Copy
# Extract email data from a file
email_data = extract_email_data("./emails/email1.eml")

# Perform classification
classification = find_benefits(prompt, email_data)

# Perform attribute extraction
attributes = find_attributes(prompt, email_data)
Performance:
After classification and attribute extraction, the model's performance is evaluated using the classification_report from scikit-learn.

Notes:
Ensure pdf2image and Tesseract OCR are installed for PDF/image attachments.

Use a local server running the Llama 3.1 model (e.g., via Ollama API) for classification and extraction tasks.

License:
This project is licensed under the MIT License.

