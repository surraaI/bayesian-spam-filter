### Documentation: Utilizing the SMS Spam Collection Dataset for Spam Classification

#### 1. Dataset Overview
The SMS Spam Collection v.1 is a tagged dataset consisting of 5,574 SMS messages, labeled as `ham` (legitimate) or `spam`. The dataset serves as a foundational resource for SMS spam research and machine learning applications.

##### 1.1 Data Compilation
The dataset was curated from several sources:
- Grumbletext (UK Forum): Contains 425 spam messages extracted manually from user claims.
- Caroline Tag’s PhD Thesis: Includes 450 legitimate (ham) messages.
- NUS SMS Corpus: Features 3,375 legitimate messages collected from students at the National University of Singapore.
- SMS Spam Corpus v.0.1 Big: Provides 1,002 legitimate and 322 spam messages.

##### 1.2 Data Distribution
- Ham Messages: 4,827 (86.6%)
- Spam Messages: 747 (13.4%)

##### 1.3 Data Format
- Each line in the dataset consists of two columns:
  1. Label: `ham` or `spam`
  2. Message: The raw text of the SMS

Example:
```
ham   What you doing?how are you?
spam  FreeMsg: Txt: CALL to No: 86888 & claim your reward...
```

#### 2. Utilizing Prior Knowledge in Spam Classification
##### 2.1 The Role of Prior Knowledge
Prior knowledge represents the baseline probabilities of a message being spam or ham. These probabilities are essential for probabilistic classification models, such as Naive Bayes, to determine the likelihood of labels given the message content.

##### 2.2 Calculating Priors
The priors are derived from the dataset as follows:
- P(ham) = Count of ham messages / Total messages
- P(spam) = Count of spam messages / Total messages

Code Snippet:
```python
total_messages = len(train_data)
spam_messages = len(train_data[train_data['label'] == 'spam'])
ham_messages = len(train_data[train_data['label'] == 'ham'])

prior_spam = spam_messages / total_messages
prior_ham = ham_messages / total_messages
print(f"P(spam): {prior_spam}, P(ham): {prior_ham}")
```

##### 2.3 Significance in Classification
- Bias Adjustment: Adjusts predictions based on the imbalanced nature of the dataset (ham dominates).
- Enhanced Accuracy: Improves classification by accounting for base rates of spam and ham messages, especially in cases where word occurrences are sparse or ambiguous.

##### 2.4 Integration with Machine Learning
The priors are combined with word likelihoods in a Bayesian framework to calculate the posterior probability for each label. This ensures that the classifier balances observed word frequencies with overall message distributions.

#### 3. Dataset Usage Guidelines
- Reference Requirement: Cite the dataset's source paper and website in any publications:
  - Almeida, T.A., Gómez Hidalgo, J.M., Yamakami, A. *Contributions to the study of SMS Spam Filtering: New Collection and Results*. (2011, ACM DOCENG).
  - Dataset URL: [SMS Spam Collection](http://www.dt.fee.unicamp.br/~tiago/smsspamcollection/)

- Ethical Use: Messages were collected with consent for public research, ensuring ethical compliance in studies.

