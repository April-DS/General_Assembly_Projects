
![img](https://camo.githubusercontent.com/2a37cbc96d036ecc447f5a2324342d442f34e2c5/68747470733a2f2f6769746875622e636f6d2f417072696c2d44532f47656e6572616c5f417373656d626c795f50726f6a656374732f626c6f622f6d61737465722f70726f6a6563745f335f5265646469742f696d616765732f7265646469742d312d6c6f676f2d706e672d7472616e73706172656e742e6a70673f7261773d74727565)

# Reddit APIs & Classification

Files in data:
- [psy_astro.csv](https://raw.githubusercontent.com/April-DS/General_Assembly_Projects/master/project_3_Reddit/data/psy_astro.csv) - Scraped data from [reddit.com](https://www.reddit.com/) subredditsL psychology, astrology
- [clean_subreddits.csv](https://raw.githubusercontent.com/April-DS/General_Assembly_Projects/master/project_3_Reddit/data/clean_subreddits.csv) - Cleaned dataset with dropped duplicates

## Content:

1. [Problem statement](https://render.githubusercontent.com/view/ipynb?commit=5dd4a4f7ca50aab0826b54c861371d6990a53591&enc_url=68747470733a2f2f7261772e67697468756275736572636f6e74656e742e636f6d2f417072696c2d44532f47656e6572616c5f417373656d626c795f50726f6a656374732f356464346134663763613530616162303832366235346338363133373164363939306135333539312f70726f6a6563745f335f5265646469742f5265646469745f636c617373696669636174696f6e2e6970796e62&nwo=April-DS%2FGeneral_Assembly_Projects&path=project_3_Reddit%2FReddit_classification.ipynb&repository_id=256115187&repository_type=Repository#Problem-statement)
2. [Library importing](https://render.githubusercontent.com/view/ipynb?commit=5dd4a4f7ca50aab0826b54c861371d6990a53591&enc_url=68747470733a2f2f7261772e67697468756275736572636f6e74656e742e636f6d2f417072696c2d44532f47656e6572616c5f417373656d626c795f50726f6a656374732f356464346134663763613530616162303832366235346338363133373164363939306135333539312f70726f6a6563745f335f5265646469742f5265646469745f636c617373696669636174696f6e2e6970796e62&nwo=April-DS%2FGeneral_Assembly_Projects&path=project_3_Reddit%2FReddit_classification.ipynb&repository_id=256115187&repository_type=Repository#*Library-importing*)
3. [Data scraping](https://render.githubusercontent.com/view/ipynb?commit=5dd4a4f7ca50aab0826b54c861371d6990a53591&enc_url=68747470733a2f2f7261772e67697468756275736572636f6e74656e742e636f6d2f417072696c2d44532f47656e6572616c5f417373656d626c795f50726f6a656374732f356464346134663763613530616162303832366235346338363133373164363939306135333539312f70726f6a6563745f335f5265646469742f5265646469745f636c617373696669636174696f6e2e6970796e62&nwo=April-DS%2FGeneral_Assembly_Projects&path=project_3_Reddit%2FReddit_classification.ipynb&repository_id=256115187&repository_type=Repository#Data-scraping)
4. [Data cleaning](https://render.githubusercontent.com/view/ipynb?commit=5dd4a4f7ca50aab0826b54c861371d6990a53591&enc_url=68747470733a2f2f7261772e67697468756275736572636f6e74656e742e636f6d2f417072696c2d44532f47656e6572616c5f417373656d626c795f50726f6a656374732f356464346134663763613530616162303832366235346338363133373164363939306135333539312f70726f6a6563745f335f5265646469742f5265646469745f636c617373696669636174696f6e2e6970796e62&nwo=April-DS%2FGeneral_Assembly_Projects&path=project_3_Reddit%2FReddit_classification.ipynb&repository_id=256115187&repository_type=Repository#Data-cleaning)
5. [Data Dictionary](https://render.githubusercontent.com/view/ipynb?commit=5dd4a4f7ca50aab0826b54c861371d6990a53591&enc_url=68747470733a2f2f7261772e67697468756275736572636f6e74656e742e636f6d2f417072696c2d44532f47656e6572616c5f417373656d626c795f50726f6a656374732f356464346134663763613530616162303832366235346338363133373164363939306135333539312f70726f6a6563745f335f5265646469742f5265646469745f636c617373696669636174696f6e2e6970796e62&nwo=April-DS%2FGeneral_Assembly_Projects&path=project_3_Reddit%2FReddit_classification.ipynb&repository_id=256115187&repository_type=Repository#Data-Dictionary)
6. [Text preprocessing](https://render.githubusercontent.com/view/ipynb?commit=5dd4a4f7ca50aab0826b54c861371d6990a53591&enc_url=68747470733a2f2f7261772e67697468756275736572636f6e74656e742e636f6d2f417072696c2d44532f47656e6572616c5f417373656d626c795f50726f6a656374732f356464346134663763613530616162303832366235346338363133373164363939306135333539312f70726f6a6563745f335f5265646469742f5265646469745f636c617373696669636174696f6e2e6970796e62&nwo=April-DS%2FGeneral_Assembly_Projects&path=project_3_Reddit%2FReddit_classification.ipynb&repository_id=256115187&repository_type=Repository#Text-preprocessing)
7. [Exploratory Data Analysis](https://render.githubusercontent.com/view/ipynb?commit=5dd4a4f7ca50aab0826b54c861371d6990a53591&enc_url=68747470733a2f2f7261772e67697468756275736572636f6e74656e742e636f6d2f417072696c2d44532f47656e6572616c5f417373656d626c795f50726f6a656374732f356464346134663763613530616162303832366235346338363133373164363939306135333539312f70726f6a6563745f335f5265646469742f5265646469745f636c617373696669636174696f6e2e6970796e62&nwo=April-DS%2FGeneral_Assembly_Projects&path=project_3_Reddit%2FReddit_classification.ipynb&repository_id=256115187&repository_type=Repository#Exploratory-Data-Analysis)
8. [Text analysis](https://render.githubusercontent.com/view/ipynb?commit=5dd4a4f7ca50aab0826b54c861371d6990a53591&enc_url=68747470733a2f2f7261772e67697468756275736572636f6e74656e742e636f6d2f417072696c2d44532f47656e6572616c5f417373656d626c795f50726f6a656374732f356464346134663763613530616162303832366235346338363133373164363939306135333539312f70726f6a6563745f335f5265646469742f5265646469745f636c617373696669636174696f6e2e6970796e62&nwo=April-DS%2FGeneral_Assembly_Projects&path=project_3_Reddit%2FReddit_classification.ipynb&repository_id=256115187&repository_type=Repository#Text-analysis)
9. [Modeling](https://render.githubusercontent.com/view/ipynb?commit=5dd4a4f7ca50aab0826b54c861371d6990a53591&enc_url=68747470733a2f2f7261772e67697468756275736572636f6e74656e742e636f6d2f417072696c2d44532f47656e6572616c5f417373656d626c795f50726f6a656374732f356464346134663763613530616162303832366235346338363133373164363939306135333539312f70726f6a6563745f335f5265646469742f5265646469745f636c617373696669636174696f6e2e6970796e62&nwo=April-DS%2FGeneral_Assembly_Projects&path=project_3_Reddit%2FReddit_classification.ipynb&repository_id=256115187&repository_type=Repository#Modeling)
10. [Best model evaluation](https://render.githubusercontent.com/view/ipynb?commit=5dd4a4f7ca50aab0826b54c861371d6990a53591&enc_url=68747470733a2f2f7261772e67697468756275736572636f6e74656e742e636f6d2f417072696c2d44532f47656e6572616c5f417373656d626c795f50726f6a656374732f356464346134663763613530616162303832366235346338363133373164363939306135333539312f70726f6a6563745f335f5265646469742f5265646469745f636c617373696669636174696f6e2e6970796e62&nwo=April-DS%2FGeneral_Assembly_Projects&path=project_3_Reddit%2FReddit_classification.ipynb&repository_id=256115187&repository_type=Repository#Best-model-evaluation)
11. [Word inspection](https://render.githubusercontent.com/view/ipynb?commit=5dd4a4f7ca50aab0826b54c861371d6990a53591&enc_url=68747470733a2f2f7261772e67697468756275736572636f6e74656e742e636f6d2f417072696c2d44532f47656e6572616c5f417373656d626c795f50726f6a656374732f356464346134663763613530616162303832366235346338363133373164363939306135333539312f70726f6a6563745f335f5265646469742f5265646469745f636c617373696669636174696f6e2e6970796e62&nwo=April-DS%2FGeneral_Assembly_Projects&path=project_3_Reddit%2FReddit_classification.ipynb&repository_id=256115187&repository_type=Repository#Word-inspection)
12. [Misclassification analisys](https://render.githubusercontent.com/view/ipynb?commit=5dd4a4f7ca50aab0826b54c861371d6990a53591&enc_url=68747470733a2f2f7261772e67697468756275736572636f6e74656e742e636f6d2f417072696c2d44532f47656e6572616c5f417373656d626c795f50726f6a656374732f356464346134663763613530616162303832366235346338363133373164363939306135333539312f70726f6a6563745f335f5265646469742f5265646469745f636c617373696669636174696f6e2e6970796e62&nwo=April-DS%2FGeneral_Assembly_Projects&path=project_3_Reddit%2FReddit_classification.ipynb&repository_id=256115187&repository_type=Repository#Misclassification-analisys)
13. [Further research suggestions](https://render.githubusercontent.com/view/ipynb?commit=5dd4a4f7ca50aab0826b54c861371d6990a53591&enc_url=68747470733a2f2f7261772e67697468756275736572636f6e74656e742e636f6d2f417072696c2d44532f47656e6572616c5f417373656d626c795f50726f6a656374732f356464346134663763613530616162303832366235346338363133373164363939306135333539312f70726f6a6563745f335f5265646469742f5265646469745f636c617373696669636174696f6e2e6970796e62&nwo=April-DS%2FGeneral_Assembly_Projects&path=project_3_Reddit%2FReddit_classification.ipynb&repository_id=256115187&repository_type=Repository#Further-research-suggestions)

## Data Dictionary

| Feature name | Type           | Description                                |
| :----------- | :------------- | :----------------------------------------- |
| text         | str            | Title + self text of post                  |
| num_comments | int            | Number of comments under a post            |
| ups          | int            | Number of ups of post                      |
| date         | datetime64[ns] | Date of publication of post                |
| subreddit    | str            | Name of subreddit (Psychology / Astrology) |


## Problem statement

Some people [claim](https://qz.com/1170481/horoscopes-2018-astrology-isnt-fake-its-just-been-ruined-by-modern-psychology/) that psychology and astrology are very similar fields:

```
Astrology’s contemporary flavour has a closer relationship with the social science of psychology than the observational science it used to be based upon.
```

Modern Astrology uses a psychological approach and language when clients’ horoscopes are interpreted which can be misleading for people.

Other people think that psychology is science while astrology is a pseudoscience and they do not have any close relationship.

[Astrology](https://en.wikipedia.org/wiki/Astrology) consists of a number of belief systems that hold that there is a relationship between astronomical phenomena and events or descriptions of personality in the human world.

[Psychology](https://en.wikipedia.org/wiki/Psychology) is the scientific study of the human mind and its functions.

#### Aim Of The Project:

- Classify new posts from two subreddits: [r/psychology/](https://www.reddit.com/r/psychology/) and [r/astrology/](https://www.reddit.com/r/astrology/).
- Sorting more predictive words of subreddits based on a coefficient of the model.
- Provide recommendations for further research.

#### Answer the following questions:

- Is it possible to distinguish post about psychology and astrology based on the text?
- Do psychology and astrology have a specific vocabulary?
- Does the activity of the community members in subreddits differ?
- Do psychological posts contain scientific words?

### Evaluation of a model

Models are evaluated by **Classification accuracy, precision, recall and f1 score**.

[Accuracy](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.accuracy_score.html) is the total percent of predictions a model gets right.

![$$\text{Accuracy}={\frac{True Positive + True Negative}{True Positive + True Negative + False Positive + False Negative}}$$](https://render.githubusercontent.com/render/math?math=%5Ctext%7BAccuracy%7D%3D%7B%5Cfrac%7BTrue%20Positive%20%2B%20True%20Negative%7D%7BTrue%20Positive%20%2B%20True%20Negative%20%2B%20False%20Positive%20%2B%20False%20Negative%7D%7D&mode=display)

[Precision](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.precision_score.html) is the ratio of correctly predicted positive observations to the total predicted positive observations.

![$$\text{Precision}={\frac{True Positive}{True Positive + False Positive}}$$](https://render.githubusercontent.com/render/math?math=%5Ctext%7BPrecision%7D%3D%7B%5Cfrac%7BTrue%20Positive%7D%7BTrue%20Positive%20%2B%20False%20Positive%7D%7D&mode=display)

[Recall](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.recall_score.html) is the ratio of correctly predicted positive observations to the all observations in positive class.

![$$\text{Recall = Sensitivity}={\frac{True Positive}{True Positive + False Negative}}$$](https://render.githubusercontent.com/render/math?math=%5Ctext%7BRecall%20%3D%20Sensitivity%7D%3D%7B%5Cfrac%7BTrue%20Positive%7D%7BTrue%20Positive%20%2B%20False%20Negative%7D%7D&mode=display)

[F1](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.f1_score.html) score is weighted average of the precision and recall. F1 score reaches its best value at 1 and worst score at 0.

![$$\text{Recall = Sensitivity}={\frac{2 * Precision * Recall}{Precision + Recall}}$$](https://render.githubusercontent.com/render/math?math=%5Ctext%7BRecall%20%3D%20Sensitivity%7D%3D%7B%5Cfrac%7B2%20%2A%20Precision%20%2A%20Recall%7D%7BPrecision%20%2B%20Recall%7D%7D&mode=display)

### Model description:

Best model: Logistic Regression with TFidFVectorizer. Models performed: Logistic Regression, KNeighborsClassifier, Naive Bayes (MultinomialNB). Vectorizers: CountVectorizer, TfidfVectorizer.

Feature for classification: text of subreddits.

Target variable: subreddits: 1- psychology, 0 - astrology.

Features for EDA: number of comments, number of ups, length of text, date of publication.

### The resulting model can be useful for

- layman people who cannot decide if the information comes from psychological science or astrological pseudoscience.
- Moderators of r/psychology/ and r/astrology/ subreddits to save time from manual sorting of these two classes.

#### The educational goals of the project:

- Using Reddit's API, collect posts from two subreddits (Psychology and Astrology).
- Use NLP to train a classifier on which subreddit a given post came from. This is a binary classification problem.


__________________________________________________
__________________________________________________

## Results[¶](http://localhost:8888/notebooks/Desktop/DataScience/General_Assembly/Workarea/classes/Projects_General_Assembly/project_3_Reddit/Reddit_classification.ipynb#Results)

LogisticRegression is the best model with TfidfVectorizer. The model is overfitted, but the test score is still very high and higher than other models. Also, LogisticRegression showed the best recall that means that classifier found almost all positive samples (psychological subreddit posts).

Metrics of LogisticRegression model:

| Train accuracy                   | Trainaccuracy | Test accuracy | Test precision | Test recall | Test f1 |
| :------------------------------- | :------------ | :------------ | :------------- | :---------- | :------ |
| 0.97, 0.933, 0.945, 0.957, 0.896 | 0.998         | 0.945         | 0.924          | 0.956       | 0.94    |

All the models perform better with TfidfVectorizer. MultinomialNB and KNeighborsClassifier also showed pretty decent scores. KNeighborsClassifier turned out to be less overfitted in comparison with others.

Misclassified posts are different but these posts contain many general vocabularies.

## Conclusion

#### Aim Of The Project:

- 820 new posts from two subreddits: [r/psychology/](https://www.reddit.com/r/psychology/) and [r/astrology/](https://www.reddit.com/r/astrology/) were classified with accuracy of 94.5 %
- Predictive words of subreddits where [identified](http://localhost:8888/notebooks/Desktop/DataScience/General_Assembly/Workarea/classes/Projects_General_Assembly/project_3_Reddit/Reddit_classification.ipynb#Word-inspection) based on a coefficient of the model.

#### Answering the following questions:

- Is it possible to distinguish post about psychology and astrology based on the text? Yes, it is. Our model classified correctly 94.5 % of new unlabeled posts.
- Does the activity of the community members in subreddits differ? Yes, it does: 1.People who write posts for an astrological subreddit prefer to use more words (and sometimes even more than 1000 words) than those who writing posts for a psychological subreddit. 2.Astrological community writing more comments to posts than psychological. 3.Psychological community is more than astrological rates posts with ups. 4.Psychological posts were published later at night than astrological. Morning activity (from 8 to 10 a.m) can be seen for astrological subreddit.
- Do psychology and astrology have a specific vocabulary? Yes, they do. Specific words for Psychology: brain, psychreg, social, health, mental, cognitive, anxiety, behavior. Specific words for Astrology: house, sign, saturn, planets, venus, placements, mars, signs, sun.
- Do psychological posts contain scientific words? Some words are from general scientific vocabulary which distinguish psychology from astrology: study, research.

## Further research suggestions

Based on the model limitation some suggestions for further research can be made:

- Scrape more data for each subreddit.
- Use fully balanced classes for better predictions.
- Use the same balance of classes as a number of all posts in subreddits for better generalization of a model.
- Use additional features such as number of comments, number of ups and length of text for extension of the model.
- Make a decision about general words: some general words can lead to misclassification.
- Make a decision about keeping specific words. Words such as psychology and astrology were removed from task complications and educational purpose only in this project.
- Filter posts with a small number of words in selftext and title.
- Use more advanced models.

Ideas for additional research:

- Exploring posts with a high number of commentaries and ups.
- Expend a model for more broad classification:
  - Distinguishing psychological posts from other posts with different topics.
  - Explore how psychology differs from science subreddit.
  - Add more than two classes.
- Build a model for posts with a small length of texts.
- Extend dataset with posts which were published during a longer period of time.
- Deploy the model for general publish usage.
