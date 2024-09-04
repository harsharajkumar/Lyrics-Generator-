# Lyrics Generator using Hugging Face Transformer
This project is a machine learning-based model that generates lyrics in the style of Drake using GPT-2. It utilizes the transformers library from Hugging Face, TensorFlow, and other essential tools for data processing, model training, and evaluation.

# Project Overview
The goal of this project is to generate lyrics similar to those of Drake using a GPT-2 model fine-tuned on a dataset of Drake's lyrics. The dataset is preprocessed, tokenized, and then used to train a language model that can generate lyrics based on the style and content of the training data.

# Installation
Clone the repository:

bash
git clone https://github.com/yourusername/drake-lyrics-generator.git
cd drake-lyrics-generator
Install the required packages:

bash
pip install -r requirements.txt
Set up your Kaggle API key to download the dataset:

Create a kaggle.json file with your Kaggle API credentials.
Move it to the appropriate location:

bash
mkdir ~/.kaggle
cp kaggle.json ~/.kaggle/
chmod 600 ~/.kaggle/kaggle.json
Download and unzip the dataset:

bash
kaggle datasets download -d juicobowley/drake-lyrics
unzip drake-lyrics.zip -d dataset/
Dataset
The dataset used in this project consists of Drake's lyrics in CSV format. The CSV file contains the following columns:

album: The album where the song belongs.
lyrics_title: The title of the lyrics.
lyrics_url: The URL to the lyrics on Genius.com.
lyrics: The lyrics text.
track_views: The number of views for the track.
Preprocessing
The lyrics are preprocessed and tokenized using the GPT2TokenizerFast from the Hugging Face transformers library. The preprocessing steps include:

Truncating the lyrics to a maximum length of 256 tokens.
Padding the sequences to ensure consistent input size.
Filtering out sequences that are too short or invalid.
Model
The model used is GPT-2, a transformer-based language model. The following steps are performed:

Load the gpt2-medium model from the Hugging Face transformers library.
Preprocess the dataset to fit the input requirements of the model.
Convert the dataset into TensorFlow format for training.
Fine-tune the GPT-2 model on the Drake lyrics dataset.
Training
The training pipeline involves:

Creating a custom data collator using DataCollatorForLanguageModeling.
Adjusting the attention mask for the input data.
Training the model using the TensorFlow tf.data pipeline.
Results
The fine-tuned GPT-2 model generates lyrics that are stylistically similar to Drake's original work. The generated lyrics can be evaluated for creativity, coherence, and similarity to the training data.

Usage
To generate lyrics using the trained model:

Load the trained model and tokenizer.
Input a prompt or seed text.
Generate the lyrics based on the input.
Contributions

Feel free to contribute to this project by:
Reporting issues.
Submitting pull requests.
Suggesting enhancements.

