# Bayesian Spam Filter

## Project Overview
This project demonstrates the implementation of **Bayesian Decision Theory** to classify email messages as spam or not spam using the **SMS Spam Collection Dataset** from the UCI Machine Learning Repository. The project uses probabilistic reasoning, leveraging prior knowledge and likelihood estimates to compute posterior probabilities and make optimal decisions.

## Features
- Implementation of Bayesian Decision Theory.
- Tokenization and preprocessing of email messages.
- Calculation of prior probabilities, likelihoods, and posterior probabilities.
- Classification of emails based on computed probabilities.
- Evaluation of the classifier using performance metrics.

## Dataset
The **SMS Spam Collection Dataset** contains labeled SMS messages categorized as either spam or ham (not spam). It is publicly available from the UCI Machine Learning Repository: [SMS Spam Collection Dataset](https://archive.ics.uci.edu/ml/datasets/sms+spam+collection).

## Project Workflow

1. **Dataset Preprocessing**
    - Load and explore the dataset.
    - Preprocess messages by tokenizing, lowercasing, and removing non-alphanumeric characters.

2. **Prior Probability Calculation**
    - Compute the probability of spam and non-spam messages based on the training data.

3. **Likelihood Estimation**
    - Calculate word frequencies in spam and non-spam messages.
    - Use Laplace smoothing to handle unseen words.

4. **Posterior Probability Computation**
    - Apply Bayes' theorem to compute the probability of a message being spam or not spam.

5. **Classification**
    - Classify messages as spam or ham based on posterior probabilities.

6. **Evaluation**
    - Measure performance using metrics such as accuracy, precision, recall, and F1-score.
    - Visualize results using a confusion matrix.

## Installation and Usage

### Prerequisites
- Python 3.7+
- Required libraries: `pandas`, `numpy`, `sklearn`, `re`, `matplotlib`, `seaborn`

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/surraaI/bayesian-spam-filter
   cd bayesian-spam-filter
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

### Usage
1. Run the script:
   ```bash
   python spam_filter.py
   ```
2. Modify parameters or test new datasets by updating the script as needed.

## Example Results

### Metrics
- **Accuracy**: ~97%
- **Precision**: 0.89
- **Recall**: 0.94
- **F1-Score**: 0.91

### Confusion Matrix
A sample confusion matrix visualizing true vs. predicted classifications:

```
          Predicted
          Ham   Spam
True Ham   1423    25
True Spam   12    212
```

## Project Structure
```
.
├── sms+spam+collection
│   └── SMSSpamCollection  # Dataset file
├── spam_filter.ipynb         # Main implementation script
├── README.md               # Project documentation
```

## Key Functions in the Code
- **`preprocess_text`**: Preprocesses text messages for analysis.
- **`likelihood`**: Computes likelihood of a word given the class (spam or not spam).
- **`classify`**: Classifies a message as spam or ham based on posterior probabilities.

## Future Enhancements
- Integrate additional NLP techniques like stemming or lemmatization.
- Expand to multilingual datasets.
- Implement a GUI for easier interaction with the spam filter.

## References
- [Bayesian Decision Theory - Wikipedia](https://en.wikipedia.org/wiki/Bayesian_decision_theory)
- [SMS Spam Collection Dataset - UCI](https://archive.ics.uci.edu/ml/datasets/sms+spam+collection)

---

### Author
Sura Itana


