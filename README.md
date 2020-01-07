# News-Title-Classification-Model
A text classification model used to classify news title into classes: story, ask-hn, show-hn and poll with the help of the concept of natural language processing(NLP). Further experiments are done to improve the performance of the baseline-model.

## Inputs
- **CSV data file**: Dataset taken from Hacker News posts from 2018-2019. 
- **StopWords file**: File containing the stop words removed in experiment 1.
- **Frequency value**: Value inputted in experiment 4(a).
- **Percentage value**: Value inputted in experiment 4(b).
- **Smoothing value**: Value inputted in experiment 5.

## How to run?
- Set up an environment and install the libraries: [Pandas](https://pypi.org/project/pandas/),[NLTK](https://www.nltk.org/), [Matplotlib](https://matplotlib.org/), [Sklearn](https://scikit-learn.org/) and [NumPy](https://numpy.org/).
- Open a new [Jupyter notebook](https://jupyter.org/) and paste the code.
- Keep the related files like dataset file and stop words file in the same folder.
- Run the code.
- For experiment 1, put all variables to false.
- For experiment 2, put all variables to false and stopwords_filter as true.
- For experiment 3, put all variables to false and wordlength_filter as true.
- For experiment 4(a), put all variables to false and infreqword_filter_a as true.
- For experiment 4(b), put all variables to false and infreqword_filter_b as true.
- For experiment 5, put all variables to false and change the values for delta.

## Working
The dataset is divided into training and testing data where training data is the posts from 2018 and testing is from 2019. The data was further cleaned and processed using NLP techniques like tokenization, lemmatization, creating vocabulary and model. The model used an implementation of Naïve Bays Classifier with additive smoothing to classify based on the created vocabulary and cleaned dataset. Further, model is tested on the testing dataset and following experiments are done:
- **Experiment 1**: Baseline experiment where no change is made with smoothing factor as 0.5. The accuracy was 98%.
<img src="https://github.com/DhwaniSondhi/News-Title-Classification-Model/blob/master/results/baseline/pic.PNG" width="550" height="400"/>

- **Experiment 2**: Given list of stop words are removed. The accuracy was increased as compared to the baseline experiment. 
<br/>
<img src="https://github.com/DhwaniSondhi/News-Title-Classification-Model/blob/master/results/StopWord/pic.PNG" width="550" height="400"/>

- **Exeripment 3**: All vocabulary words with length ≤2 and length ≥ 9 are removed. The accuracy decrease is explaining the behavior of removal of informative words from vocab resulting in underfitting of the model.
<br/>
<img src="https://github.com/DhwaniSondhi/News-Title-Classification-Model/blob/master/results/WordFiltering/pic.PNG" width="550" height="400"/>

- **Exeripment 4(a)**: All vocabulary words are removed gradually with frequency=1, frequency ≤ 5, frequency ≤ 10, frequency ≤ 15 and frequency ≤ 20. The accuracy is decreasing because our data set contains the least frequent number in classes such as poll, ask_hn, and show_hn. While it is true that they are also present in story class but removing words from other three classes will hit the accuracy and will be more biased towards story.
<img src="https://github.com/DhwaniSondhi/News-Title-Classification-Model/blob/master/results/Least%20Frequent%20Words/pic.PNG" width="550" height="400"/>

- **Exeripment 4(b)**: All vocabulary words are removed gradually with top 5% most frequent words, the 10% most frequent words, 15%, 20% and 25% most frequent words. The accuracy decreased at high rate initially as the experiment greatly affected story class and caused misclassification.
<img src="https://github.com/DhwaniSondhi/News-Title-Classification-Model/blob/master/results/Most%20Frequent%20Words/pic.PNG" width="550" height="400"/>

- **Exeripment 5**: The smoothing factor is changed from 0.0 to 0.9. Following was the effect:
<img src="https://github.com/DhwaniSondhi/News-Title-Classification-Model/blob/master/results/Smoothing/pic.PNG" width="550" height="400"/>

[More Results(vocabulary, model) for each experiment](https://github.com/DhwaniSondhi/News-Title-Classification-Model/tree/master/results)
<br/>
[Further details of the project](https://github.com/DhwaniSondhi/News-Title-Classification-Model/blob/master/docs/Project_Report.pdf)
