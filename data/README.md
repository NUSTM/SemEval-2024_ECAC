# Dataset for SemEval-2024 Task 3

The dataset ECF 2.0 for [**SemEval-2024 Task 3: Multimodal Emotion Cause Analysis in Conversations**](https://aclanthology.org/2024.semeval-1.277) is released here.

In our preliminary work [MECPE](https://github.com/NUSTM/MECPE), we constructed the **ECF (1.0)** dataset. For this SemEval competition, the entire ECF (1.0) dataset serves as the training data, and we have **additionally annotated a test set** as the evaluation data, together constituting the **ECF 2.0** dataset.


## File Description

- The files `Subtask_1_train.json` and `Subtask_2_train.json` contain the training data for two subtasks in SemEval 2024, where all instances are stacked into a list and each of them is stored in a dictionary. The files `Subtask_1_test.json` and `Subtask_2_test.json` contain the evaluation data, using the same format. 
- For Subtask 2, you can refer to the JSON files to obtain **timestamps** and download the raw videos from the website to process the multimodal data.  ⚠️ **Due to potential copyright issues, we do not provide pre-segmented video clips.**

📢 Note: To ensure the fairness of our competition, the evaluation data released during the evaluation phase of SemEval 2024 included some noise data that was not intended for evaluation. In the newly released version, the noise data has been removed, and the labels have been made publicly available.

## Dataset Statistics

|           | Training Data           | Evaluation data        |
| ----------------------------------------- | ----------------------------------------- | --------------------------------------- |
| # of conversations | 1,374 | 341 |
| # of utterances | 13,619 | 3,101 |
