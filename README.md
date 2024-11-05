# SemEval-2024 Task 3: Multimodal Emotion Cause Analysis in Conversations

[![Dataset](https://img.shields.io/badge/Dataset-🤗_Hugging_Face-F0A336)](https://huggingface.co/datasets/NUSTM/ECF) [![Conference](https://img.shields.io/badge/Paper-SemEval--2024-D93B2E)](https://aclanthology.org/2024.semeval-1.277/) [![Conference](https://img.shields.io/badge/Paper-arXiv:2405.13049-A42F22)](https://arxiv.org/abs/2405.13049) [![Website](https://img.shields.io/badge/Competition-CodaLab-7AC5F0)](https://codalab.lisn.upsaclay.fr/competitions/16141) [![Website](https://img.shields.io/badge/Group-Google-4C7DE8)](https://groups.google.com/g/ecf_eca)

We organize an ECAC evaluation, namely Multimodal Emotion Cause Analysis in Conversations, as a shared task of [SemEval-2024](https://semeval.github.io/SemEval2024/tasks).

🎉🎉🎉 Our **task paper** is available [here](https://aclanthology.org/2024.semeval-1.277/). Please [cite](#Citation) it according to the official format.

🌟🌟🌟 We welcome interested colleagues to join our [Google Group](https://groups.google.com/g/ecf_eca) and submit their results to our [CodaLab Competition](#CodaLab) website.


## Task

![example](https://github.com/NUSTM/SemEval-2024_ECAC/raw/main/example.png)

Based on the multimodal conversational emotion cause dataset [ECF](https://github.com/NUSTM/MECPE), we define the following two subtasks:

### Subtask 1: Textual Emotion-Cause Pair Extraction in Conversations
In this subtask, an emotion cause is defined and annotated as a textual span. 

- Input: a conversation containing the **speaker** and the **text** of each utterance.
- Output: all emotion-cause pairs, where each pair contains an **emotion utterance** along with its **emotion category** and the **textual cause span** in a specific **cause utterance**, e.g., (U3\_Joy, U2\_"You made up!").

### Subtask 2: Multimodal Emotion-Cause Pair Extraction in Conversations

It should be noted that sometimes the cause can not be reflected in text only, and we accordingly propose a multimodal subtask to extract emotion cause in all three modalities (language, audio, and vision). For example, the cause for Phoebe’s Disgust in U5 is that Monica and Chandler were kissing in front of her, which is reflected in the visual modality of U5. In this case, cause is defined and annotated at the utterance level.

- Input: a conversation including the **speaker**, **text**, and **audio-visual clip** for each utterance.
- Output: all emotion-cause pairs, where each pair contains an **emotion utterance** along with its **emotion category** and a **cause utterance**, e.g., (U5\_Disgust, U5).

## <span id="Dataset">Dataset</span>

To access the dataset **ECF 2.0**, please refer to the [data](https://github.com/NUSTM/SemEval-2024_ECAC/tree/main/data) folder.

- **Training data**: the ECF dataset
- **Evaluation data**: the additionally annotated test set

❗️❗️❗️ Please ensure that the data is used exclusively for research purposes!

🔔 Note that the use of additional annotation data is not allowed for ECAC. However, we encourage participants to utilize publicly available Large Language Models, including ChatGPT, during the system development and evaluation phases.


## Evaluation Metrics

- Similar to the previous works, we evaluate the emotion-cause pairs of each emotion category with **F1** scores separately and further calculate a weighted average of F1 scores across the six emotion categories (*Anger*, *Disgust*, *Fear*, *Joy*, *Sadness* and *Surprise*).
- For Subtask 1 which involves the textual cause span, we adopt two strategies to determine whether the span is extracted correctly: Strict Match (the predicted span should be exactly the same as the annotated span) and Proportional Match (considering the overlap proportion between the predicted span and the annotated one).

📢 You can find the details of the evaluation metrics on [GitHub](https://github.com/NUSTM/SemEval-2024_ECAC/blob/main/CodaLab/evaluation).


## <span id="CodaLab">CodaLab</span>

Our [CodaLab Competition](https://codalab.lisn.upsaclay.fr/competitions/16141) website is available! Please refer to the [official instructions](https://github.com/SemEval/SemEval2024/blob/main/codalab.md#participating-in-a-codalab-competition) on how to participate in the competition. After registering for our competition on Codalab, please fill in your registered user information on the [online form](https://docs.google.com/spreadsheets/d/1Xq_ByQev4C-la3YP9Kql6186ciH-X9yIU6pJxhJalXc/edit?usp=sharing).

## Important Dates

| Event | Date                                       |
| :-------------------------------------------- | :-------------------------------------------------- |
| ~~Tasks announced (with sample data available)~~ | ~~17 July 2023~~                                      |
| ~~Training data ready~~                          | ~~4 September 2023~~                                   |
| ~~Practice start on CodaLab~~                        | ~~01 December 2023~~                                  |
| ~~Evaluation start~~                             | ~~15 January 2024~~                                    |
| ~~Evaluation end~~                               | ~~31 January 2024~~                                    |
| ~~Paper submission due~~                         | ~~19 February 2024~~                                   |
| ~~Notification to authors~~                      | ~~18 March 2024~~                                       |
| ~~Camera ready due~~                             | ~~01 April 2024~~                                      |
| ~~SemEval workshop~~                             | ~~20–21 June 2024 (co-located with NAACL 2024)~~ |

Note: All deadlines are 23:59 UTC-12 (AoE).


## Organizers
- [Rui Xia](http://www.nustm.cn/member/rxia/index.html)
- [Jianfei Yu](https://sites.google.com/site/jfyu1990/)
- [Fanfan Wang](https://scholar.google.com/citations?view_op=list_works&hl=zh-CN&hl=zh-CN&user=bG1H7OQAAAAJ)
- [Erik Cambria](https://dr.ntu.edu.sg/cris/rp/rp00927)


## <span id="Citation">Citation</span>
```
@ARTICLE{wang2023multimodal,
  author={Wang, Fanfan and Ding, Zixiang and Xia, Rui and Li, Zhaoyu and Yu, Jianfei},
  journal={IEEE Transactions on Affective Computing}, 
  title={Multimodal Emotion-Cause Pair Extraction in Conversations}, 
  year={2023},
  volume={14},
  number={3},
  pages={1832-1844},
  doi = {10.1109/TAFFC.2022.3226559}
}

@InProceedings{wang2024SemEval,
  author={Wang, Fanfan  and  Ma, Heqing  and  Xia, Rui  and  Yu, Jianfei  and  Cambria, Erik},
  title = "{S}em{E}val-2024 Task 3: Multimodal Emotion Cause Analysis in Conversations",
  booktitle = "Proceedings of the 18th International Workshop on Semantic Evaluation (SemEval-2024)",
  month = jun,
  year = "2024",
  address = "Mexico City, Mexico",
  publisher = "Association for Computational Linguistics",
  url = "https://aclanthology.org/2024.semeval-1.277",
  pages = "2039--2050",
}

@article{wang2024semeval,
  title={Semeval-2024 task 3: Multimodal emotion cause analysis in conversations},
  author={Wang, Fanfan and Ma, Heqing and Yu, Jianfei and Xia, Rui and Cambria, Erik},
  journal={arXiv preprint arXiv:2405.13049},
  year={2024}
}
```
