# SemEval-2024 Task 3: The Competition of Multimodal Emotion Cause Analysis in Conversations

We organize an ECAC evaluation, namely the Competition of Multimodal Emotion Cause Analysis in Conversations, as a shared task of [SemEval-2024](https://semeval.github.io/SemEval2024/tasks).

🔥🔥🔥 Our [CodaLab Competition](#CodaLab) website is available!

❗️❗️❗️ The **task** has been updated! After careful consideration, we have decided to remove the Emotion Cause Extraction (ECE) task from the competition. The specific reasons have been explained in our group.

<!---🔥🔥🔥 [Training set](#Dataset) has been released!-->

🌟🌟🌟 Interested participants are encouraged to <!--- register via [Google Form](https://forms.gle/ioFAFTbuMtoRM7yd6) and  -->join our [Google Group](https://groups.google.com/g/ecf_eca) to stay updated.

<!--- **Registration Form:** [](https://forms.gle/ioFAFTbuMtoRM7yd6)
**Mailing List:** [ecf_eca@groups.google.com](https://groups.google.com/g/ecf_eca)
**[TRIAL]** The sample data are uploaded to [Google Drive](https://drive.google.com/drive/folders/16jCk5o4dp0ew5ce-ewEEJ_v6bOPFJinC?usp=sharing). -->


## Task
<!---
We first clarify the definitions of emotion and cause before introducing the task. 
- **Emotion** is a psychological state associated with thought, feeling and behavioral response. In conversations, emotions are usually annotated at the utterance level. In our dataset, emotion categories are Ekman’s six basic emotions including *Anger*, *Disgust*, *Fear*, *Joy*, *Sadness* and *Surprise*. 
- **Cause** refers to the objective event or subjective argument that triggers the corresponding emotion.
-->

![example](https://github.com/NUSTM/SemEval-2024_ECAC/raw/main/example.png)

Based on the multimodal conversational emotion cause dataset [ECF](https://github.com/NUSTM/MECPE), we define the following two subtasks:

### Subtask 1: Textual Emotion-Cause Pair Extraction in Conversations
In this subtask, an emotion cause is defined and annotated as a textual span. 

- Input: a conversation containing the **speaker** and the **text** of each utterance.
- Output: all emotion-cause pairs, where each pair contains an **emotion utterance** along with its **emotion category** and the **textual cause span** in a specific **cause utterance**, e.g., (U3\_Joy, U2\_"You made up!").

### Subtask 2: Multimodal Emotion Cause Analysis in Conversations

It should be noted that sometimes the cause can not be reflected in text only, and we accordingly propose a multimodal subtask to extract emotion cause in all three modalities (language, audio, and vision). For example, the cause for Phoebe’s Disgust in U5 is that Monica and Chandler were kissing in front of her, which is reflected in the visual modality of U5. In this case, cause is defined and annotated at the utterance level.

- Input: a conversation including the **speaker**, **text**, and **audio-visual clip** for each utterance.
- Output: all emotion-cause pairs, where each pair contains an **emotion utterance** along with its **emotion category** and a **cause utterance**, e.g., (U5\_Disgust, U5).

## <span id="Dataset">Dataset</span>

🔔 Please note that the use of additional annotation data is not allowed for ECAC. However, we encourage participants to utilize publicly available Large Language Models, including ChatGPT, during the system development and evaluation phases.

- [Training data](https://drive.google.com/drive/folders/1TIRBiL8z4ZnoxtuKM8pnjtm2BxB5mS4Y?usp=sharing).
- [Trial data](https://drive.google.com/file/d/1Hf4qULr5CjxOiBglNC6OTLf1LFJxSDjU/view?usp=share_link) for the Practice phase on CodaLab
- Evaluation data will be released on January 10, 2024.

📢 Trial data and evaluation data contain some noise instances that will not be evaluated.

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
| Practice start on CodaLab                        | 01 December 2023                                    |
| Evaluation start                             | 15 January 2024                                    |
| Evaluation end                               | 31 January 2024                                    |
| Paper submission due                         | 19 February 2024                                   |
| Notification to authors                      | 01 April 2024                                       |
| Camera ready due                             | 22 April 2024                                      |
| SemEval workshop                             | 16–21 June 2024 (co-located with NAACL 2024) |

Note: All deadlines are 23:59 UTC-12 (AOE).


## Organizers
- [Rui Xia](http://www.nustm.cn/member/rxia/index.html)
- [Jianfei Yu](https://sites.google.com/site/jfyu1990/)
- <a href="mailto:ffwang@njust.edu.cn">Fanfan Wang</a>
- [Erik Cambria](https://dr.ntu.edu.sg/cris/rp/rp00927)

## Citation
```
@ARTICLE{wang2022multimodal,
  author={Wang, Fanfan and Ding, Zixiang and Xia, Rui and Li, Zhaoyu and Yu, Jianfei},
  journal={IEEE Transactions on Affective Computing}, 
  title={Multimodal Emotion-Cause Pair Extraction in Conversations}, 
  year={2022},
  pages={1-12},
  issn = {1949-3045},
  doi = {10.1109/TAFFC.2022.3226559}
}
```
