# Next Word Prediction with LSTM

A deep learning project that predicts the **next word in a text sequence** using an LSTM-based language model trained on William Shakespeare's *Hamlet*.

The project includes model training, tokenization, sequence preparation, early stopping, a saved Keras model, tokenizer, and a Streamlit web application for interactive next-word prediction.

## 🚀 Project Overview

The model learns word sequences from *Hamlet* and predicts the most likely next word for a user-provided text prompt.

Example:

```text
Input:  To be or not to
Output: be
```

The Streamlit application provides a simple interface where users can enter a sequence of words and request the model's next-word prediction.

## 🧠 Technologies Used

- Python
- TensorFlow / Keras
- LSTM (Long Short-Term Memory)
- NumPy
- Pandas
- Scikit-learn
- NLTK
- Streamlit
- Matplotlib
- TensorBoard

## 📁 Project Structure

```text
.
├── app.py
├── experiemnts.ipynb
├── hamlet.txt
├── next_word_lstm.h5
├── tokenizer.pickle
├── requirements.txt
└── README.md
```

### File Description

| File | Description |
|---|---|
| `app.py` | Streamlit application for interactive next-word prediction |
| `experiemnts.ipynb` | Notebook containing data preparation, sequence generation, model training and evaluation |
| `hamlet.txt` | Shakespeare's *Hamlet* text used as the training corpus |
| `next_word_lstm.h5` | Trained LSTM model |
| `tokenizer.pickle` | Saved tokenizer used to convert input text into sequences |
| `requirements.txt` | Python dependencies required to run the project |

## ⚙️ How It Works

The project follows this pipeline:

```text
Hamlet Text
    ↓
Text Preprocessing
    ↓
Tokenization
    ↓
Generate N-gram Sequences
    ↓
Prepare Input and Target Data
    ↓
LSTM Model
    ↓
Train with Early Stopping
    ↓
Save Model + Tokenizer
    ↓
Streamlit Application
    ↓
Predict Next Word
```

## 🏗️ Model

The project uses an LSTM-based neural network for next-word prediction.

The model uses:

- An embedding layer to represent words as dense vectors
- LSTM layers to learn sequential dependencies
- Dropout for regularization
- A final softmax layer to predict the next word

The trained model is saved as:

```text
next_word_lstm.h5
```

The tokenizer is saved separately as:

```text
tokenizer.pickle
```

The Streamlit application loads both artifacts before making predictions.

## 💻 Run Locally

### 1. Clone the repository

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
cd <YOUR_REPOSITORY_NAME>
```

### 2. Create a virtual environment

Windows:

```bash
python -m venv venv
venv\Scripts\activate
```

Linux/macOS:

```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Install dependencies

```bash
pip install -r requirements(20261006-061149).txt
```

### 4. Run the Streamlit application

```bash
streamlit run app(4).py
```

The application will open in your browser.

## 🎯 Using the Application

1. Open the Streamlit application.
2. Enter a sequence of words in the input box.
3. Click **Predict Next Word**.
4. The application displays the predicted next word.

The default example in the application is:

```text
To be or not to
```

## 📊 Dataset

The training corpus is William Shakespeare's *Hamlet*. The supplied text file contains the play's original text, including its historical spelling and formatting.

Because the model is trained on a single literary work, its predictions are primarily learned from the language patterns and vocabulary present in *Hamlet*.

## 🔬 Training

The notebook handles:

1. Loading the text corpus.
2. Tokenizing the text.
3. Creating sequential training examples.
4. Splitting the data into training and validation/test data.
5. Training the LSTM language model.
6. Using early stopping during training.
7. Saving the trained model and tokenizer.

## 🌐 Streamlit App

The application loads the trained model and tokenizer and converts user input into a padded sequence before passing it to the LSTM model.

The app uses:

```python
model = load_model("next_word_lstm.h5")
```

and loads:

```text
tokenizer.pickle
```

The prediction function prepares the input sequence, performs model inference, and returns the predicted word.

## 📌 Limitations

- The model is trained only on *Hamlet*, rather than a large general-purpose language corpus.
- Predictions are therefore domain-specific and may not produce natural modern English.
- Next-word prediction quality depends heavily on whether the input resembles patterns present in the training text.
- The model should be considered an educational deep learning project rather than a production language model.

## 🔮 Future Improvements

- Train on a much larger and more diverse text corpus.
- Experiment with larger embeddings and different LSTM configurations.
- Add top-k predictions instead of returning only one word.
- Display prediction probabilities.
- Improve text preprocessing.
- Add model evaluation metrics and training visualizations.
- Deploy the Streamlit application online.

## 👨‍💻 Project

This project demonstrates an end-to-end NLP workflow:

**Data → Preprocessing → Sequence Generation → LSTM → Training → Model Saving → Streamlit Deployment**
