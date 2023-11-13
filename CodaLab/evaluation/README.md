# Evaluation

Here we explain how the evaluation metrics are calculated.

## Subtask 1: Textual Emotion-Cause Pair Extraction in Conversations

Given a conversation, each emotion-cause pair $p_i$ in this subtask should contain five elements: index of emotion utterance ${eu}_i$, emotion category ${ec}_i$, index of cause utterance ${cu}_i$, start index of cause span ${ss}_i$, end index of cause span ${se}_i$, i,e, $p_i=[{eu}_i,{ec}_i,{cu}_i,{ss}_i,{se}_i]$.
For the textual cause span, we adopt two strategies to determine whether the span is extracted correctly: 
- **Strict Match**: the predicted span should be exactly the same as the annotated span
- **Proportional Match**: considering the overlap proportion of the predicted span and the annotated one

The evaluation script will output the results of multiple metrics, among which the main evaluation metric used for competition ranking is `w-avg. Strict F1`. 

### Strict F1
The Precision, Recall, and F1 scores are calculated as follows:
$$P=\frac{\sum CorrectPairs}{\sum PredictedPairs},$$
$$R=\frac{\sum CorrectPairs}{\sum AnnotatedPairs},$$
$$F_1=\frac{2 \times P \times R}{P+R},$$
where $\sum$ means summing over all conversations in the dataset, $PredictedPairs$ denotes the number of emotion-cause pairs predicted by the model, $AnnotatedPairs$ denotes the number of annotated emotion-cause pairs, and $CorrectPairs$ means the number of correct pairs in a conversation. A predicted pair is regarded as correct if its five elements are all the same as one of the annotated pairs.

### w-avg. Strict F1 (main)
<!-- In addition to the above micro average F1 score, we also evaluate the emotion-cause pairs of each emotion category with F1 scores separately and further calculate a weighted average of F1 scores across the six emotion categories (anger, disgust, fear, joy, sadness and surprise). -->
We first evaluate the emotion-cause pairs of each emotion category with Strict F1 scores separately:
$$P^j=\frac{\sum {CorrectPairs}^j}{\sum {PredictedPairs}^j},$$
$$R^j=\frac{\sum {CorrectPairs}^j}{\sum {AnnotatedPairs}^j},$$
$$F_1^j=\frac{2 \times P^j \times R^j}{P^j+R^j},$$
where ${*\_pairs}^j$ denotes the number of pairs with emotion category $j$, $j\in\{anger, disgust, fear, joy, sadness, surprise\}$. Then we further calculate a weighted average of Strict F1 scores across the six emotion categories:
$$F_1=\sum_{j=1}^{6} w^jF_1^j,$$
where $w^j$ is the proportion of annotated pairs with emotion category $j$, i.e., $w^j=\frac{\sum {AnnotatedPairs}^j}{\sum AnnotatedPairs}$.

### Proportional F1

Under the condition that the three elements $[{eu}_i,{ec}_i,{cu}_i]$ are the same, we match each predicted pair with one of the annotated pairs that has the maximum overlap proportion in terms of the cause span (if the predicted span overlaps with multiple annotated spans):
<!-- $${overlap}_i=len({ps}_i \cap {as}_k),$$
 -->
$${overlap}_i=\begin{cases}
len({ps}_i \cap {as}_k) & [{eu}_i,{ec}_i,{cu}_i] \text{are correct and } {ps}_i \cap {as}_k \neq \varnothing, \\
0 & \text{otherwise},
\end{cases}$$

$$k=\arg \mathop{\max}\limits_{t} \frac{len({ps}_i \cap {as}_t)}{len({as}_t)},$$

where ${ps}_ i$ and ${as}_ k$ represent the cause span in the predicted pair ${Pp}_ {i}$ and the annotated pair ${Ap}_ {k}$ respectively.
Then the proportional F1 is calculated based on the overlap length between the predicted span and the annotated span:

$$P=\frac{\sum \sum_{i} {overlap}_ {i}}{\sum \sum_{i} len({ps}_ i)},$$
$$R=\frac{\sum \sum_{i} {overlap}_ i}{\sum \sum_{t} len({as}_t)},$$
$$F_1=\frac{2 \times P \times R}{P+R},$$
where $i$ and $t$ denote the index of predicted pairs and annotated pairs in a conversation respectively.

### w-avg. Proportional F1
Similar to the w-avg. Strict F1, the w-avg. Proportional F1 is a weighted average of Proportional F1 scores across the six emotion categories.




## Subtask 2: Textual Emotion-Cause Pair Extraction in Conversations

Given a conversation, each emotion-cause pair in this subtask should contain three elements: index of emotion utterance $eu_i$, emotion category $ec_i$, index of cause utterance $cu_i$, i,e, $p_i=[eu_i,ec_i,cu_i]$.
The main evaluation metric is the `w-avg. F1`. We also calculate the micro `F1` score. A predicted pair is regarded as correct if its three elements are all the same as one of the annotated pairs.











