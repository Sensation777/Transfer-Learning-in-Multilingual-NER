Goal: use transfer learning to get NER scores for languages as followings:
UNER_Portuguese-Bosque,
UNER_Chinese-GSDSIMP,
UNER_Swedish-Talbanken,
UNER_Serbian-SET,
UNER_Slovak-SNK,
UNER_Croatian-SET,
UNER_English-EWT, 
UNER_Danish-DDT

Baseline:
for each language (data set), use the CRF model result as the baseline.

Instruction of running the script:
This main.ipynb can be run on the colab.
If you use the GPU(A100), can be done in 3 mins for each languages, and 17mins for total.

Before you run the code:
1. do not forget to "pip install datasets".
2. put the train and test data set in the colab files.
(Due to the colab is hard to use command line, so I set the languages into a set)
3. put the comparable baseline: crf_reports.txt

Output: compare_eval.txt.

This file contains: the results of each languages by using the fine tune model, the comparision with the baseline. (precision, recall, f1)
If the difference of precision, recall, f1 is positive, which means the fine tune result is butter than the baseline.

Pre-trained models: all the language use the same-pretained model and fine tune on own train set.
- name: dslim/distilbert-NER
- type: bert + NER
