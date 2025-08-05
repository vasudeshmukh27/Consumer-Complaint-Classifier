# Consumer Complaint Classifier using BERT
This project uses a pre-trained BERT model to perform text classification on consumer financial complaints, automatically categorizing them by product type. It serves as an end-to-end example of a modern NLP pipeline, from data preprocessing to model training and prediction.

## Project Overview
The core objective is to build a robust classifier that takes a consumer's complaint narrative as input and accurately predicts the financial product it relates to (e.g., "Credit card," "Mortgage," "Debt collection"). This automates the time-consuming task of manually sorting through unstructured text data.

- Technology: Python, PyTorch, Hugging Face Transformers (BERT)
- Core Task: Multi-Class Text Classification

## Getting Started
Follow these steps to set up and run the project on your local machine.
### 1. Prerequisites
- Python 3.10
- Git
### 2. Clone the Repository
```buildoutcfg
git clone https://github.com/vasudeshmukh27/Consumer-Complaint-Classifier.git
cd Consumer-Complaint-Classifier
```
### 3. Set Up the Virtual Environment
It is highly recommended to use a virtual environment to manage project dependencies.

On Windows:
```buildoutcfg
python -m venv venv
.\venv\Scripts\activate
```
On Mac/Linux:
```buildoutcfg
python3 -m venv venv
source venv/bin/activate
```
### 4. Install Dependencies
Install all the required Python libraries using the `requirements.txt` file.
```buildoutcfg
pip install -r requirements.txt
```
### 5. Download the Dataset
This project uses the Consumer Complaint Database from data.gov. The dataset is very large and is not included in this repository.
- Download the data here: Consumer Complaint Database
- After downloading, place the complaints.csv file inside the Input/ directory.

## Usage
The project workflow is divided into three main scripts.
### Step 1: Preprocess the Data
This script cleans the text data and prepares the embeddings required for training the BERT model.
```buildoutcfg
python processing.py
```
### Step 2: Train the Model
This script fine-tunes the pre-trained BERT model on the processed complaint data. The trained model will be saved for later use.
```buildoutcfg
python Engine.py
```
### Step 3: Make Predictions
Once the model is trained, you can use predict.py to classify a new, unseen complaint.
```buildoutcfg
python predict.py --test_complaint "Your sample complaint text goes here..."
```
Example:
```buildoutcfg
python predict.py --test_complaint "I am a victim of Identity Theft & currently have an Experian account that I can view my Experian Credit Report and getting notified when there is activity on my Experian Credit Report. For the past 3 days I've spent a total of approximately 9 hours on the phone with Experian. Every time I call I get transferred repeatedly and then my last transfer and automated message states to press 1 and leave a message and someone would call me. Every time I press 1 I get an automatic message stating than you before I even leave a message and get disconnected. I call Experian again, explain what is happening and the process begins again with the same end result. I was trying to have this issue attended and resolved informally but I give up after 9 hours. There are hard hit inquiries on my Experian Credit Report that are fraud, I didn't authorize, or recall and I respectfully request that Experian remove the hard hit inquiries immediately just like they've done in the past when I was able to speak to a live Experian representative in the United States. The following are the hard hit inquiries : BK OF XXXX XX/XX/XXXX XXXX XXXX XXXX  XX/XX/XXXX XXXX  XXXX XXXX  XX/XX/XXXX XXXX  XX/XX/XXXX XXXX  XXXX XX/XX/XXXX"
```
