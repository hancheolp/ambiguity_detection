

# Where do LLMs Encode the Knowledge to Assess the Ambiguity?

This is the official repository for the paper: "Where do LLMs Encode the Knowledge to Assess the Ambiguity?" (To appear in the Industry Track at [COLING 2025](https://coling2025.org/)).

## Abstract

Recently, large language models (LLMs) have shown remarkable performance across various natural language processing tasks, thanks to their vast amount of knowledge. Nevertheless, they often generate unreliable responses. A typical example is providing only one biased answer to ambiguous questions that can have various different correct answers. To address this issue, in this study, we discuss methods to detect such ambiguous samples. More specifically, we propose a classifier that uses a representation from an intermediate layer of the LLM as input. This is based on observations from previous research that representations of ambiguous samples at intermediate layers are closer to samples of relevant labels in the embedding space, but not necessarily at higher layers. The experimental results demonstrate that using representations from intermediate layers detects ambiguous input prompts more effectively than using representations from the final layer. Furthermore, this study proposes and evaluate the effectiveness of a method to train such classifiers without ambiguity labels, given that most datasets lack labels regarding the ambiguity of samples.

## Datasets for detecting ambiguous samples
The datasets used in this study are designed for detecting ambiguous samples—those that can be evaluated with multiple labels—in tasks such as NLI (Natural Language Inference) and sentiment analysis. For the NLI task, subsets of the SNLI ([Bowman et al., 2015](https://aclanthology.org/D15-1075/)) and MNLI ([Williams et al., 2018](https://aclanthology.org/N18-1101/)) datasets were utilized, while for sentiment analysis, a subset of the GoEmotions dataset was employed. Each sample has been reformatted into an instruction-based input format suitable for large language models.

### Labels
0: Clear sample, 
1: Ambiguous sample

### Dataset Statistics
| Dataset     | Split       | Clear       | Ambiguous |
|-------------|-------------|-------------|-----------|
| SNLI        | Train       | 1,935       | 1,935     |
|             | Validation  | 215         | 215       |
|             | Test        | 536         | 536       |
| MNLI        | Train       | 2,160       | 2,160     |
|             | Validation  | 240         | 240       |
|             | Test        | 602         | 602       |
| GoEmotions  | Train       | 1,683       | 1,683     |
|             | Validation  | 186         | 187       |
|             | Test        | 468         | 467       |