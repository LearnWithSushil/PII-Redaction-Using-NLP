**Overview**
This project focuses on developing a comprehensive solution for detecting and redacting Personally Identifiable Information (PII) from unstructured text data using advanced Natural Language Processing (NLP) techniques. The solution leverages spaCy's en_core_web_trf transformer-based model, along with custom rules and regular expressions, to identify and redact multiple PII entities such as email addresses, credit card numbers, phone numbers, and more. This project is ideal for organizations dealing with sensitive data, helping them to ensure data privacy and comply with regulations like GDPR and CCPA.

**Features**
PII Detection: Identifies various types of PII using pre-trained spaCy models and custom-built regex patterns.
Fine-tuning: Fine-tunes the spaCy transformer model (en_core_web_trf) to improve PII detection accuracy.
Support for Synthetic Data: Generates synthetic datasets using the Faker library, which are used to train and validate the model.
Performance Metrics: Calculates precision, recall, and F1-score to evaluate the model's performance in detecting PII.
Integration with external datasets: Combines synthetic data with existing datasets like AG News to improve generalizability.

**PII-Redaction-Using-NLP/**
│
├── config.cfg          # Configuration file for fine-tuning the spaCy model
├── train.spacy         # Training data in spaCy's binary format
├── output/             # Directory where the fine-tuned model is saved
├── pii_redaction.py    # Main script containing the code logic
├── README.md           # Documentation
├── requirements.txt    # List of dependencies
└── data/               # Directory containing synthetic and real datasets

**Usage**
1. Data Generation
The project uses the Faker library to generate synthetic data containing PII entities based on custom templates. These entities include names, email addresses, credit card numbers, IP addresses, and more. This data is used for training and fine-tuning the spaCy model.

2. Fine-tuning the spaCy Model
You can fine-tune the spaCy model using the synthetic dataset:

**Evaluation Metrics**
Metric	Description
Precision	Proportion of correctly redacted PII out of all redactions.
Recall	Proportion of actual PII that was successfully redacted.
F1 Score	Harmonic mean of precision and recall.

**Model Comparison**
The project evaluates multiple spaCy models for PII detection:

Model	Accuracy	Precision	Recall	F1 Score
en_core_web_trf	97.5%	0.98	0.97	0.975
en_core_web_lg	94.2%	0.94	0.94	0.94
en_core_web_md	90.8%	0.91	0.90	0.905

**Technologies Used**
spaCy: For NLP model fine-tuning and PII detection.
Transformers: For leveraging transformer-based architectures in NLP.
Faker: For generating synthetic PII data.
tldextract: For URL extraction and validation.
DLNValidation: For driver’s license number validation.

**Limitations**
The regex patterns might miss some edge cases of PII.
Model accuracy depends on the quality and quantity of training data.
Redaction is primarily text-based and doesn’t cover structured data formats (e.g., JSON, XML).

**Future Work**
Enhance regex patterns to cover more PII variations.
Explore advanced NLP models like BERT or RoBERTa for improved accuracy.
Develop support for other languages and non-English PII detection.
