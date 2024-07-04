# Palöri at CheckThat! 2024 Shared Task 6: GloTa - Combining GloVe Embeddings with RoBERTa for Adversarial Attack

## Abstract
This paper presents our approach and results for Shared Task 6 at CheckThat! Lab at CLEF 2024. We introduce two novel adversarial attack methods designed to evaluate the robustness of credibility assessment (CA) classifiers across five tasks: fact-checking, COVID-19 misinformation detection, propaganda detection, style-based news bias assessment, and rumor detection. Our proposed method, GloTa, which combines GloVe embeddings with RoBERTa-based substitutions, outperformed baseline methods in most tasks. Specifically, GloTa achieved the highest BODEGA scores in propaganda detection and fact-checking, indicating significant vulnerabilities in these areas.

## Introduction
The robustness of CA systems is crucial in combating misinformation and disinformation. Adversarial attacks provide a means to test and improve these systems. In this study, we propose GloTa, an attack method that leverages both GloVe embeddings and RoBERTa substitutions to generate adversarial examples. We compare GloTa with RoBERTa-ATTACK and evaluate their effectiveness using the BODEGA scoring framework, which measures attack success while preserving the original text's meaning.

## Methodology

### Attack Methods
1. **RoBERTa-ATTACK**: An attack method based on the RoBERTa model, focusing on generating adversarial examples by substituting words in the original text.
2. **GloTa**: Our novel method that combines GloVe embeddings with RoBERTa substitutions to create more effective adversarial examples.

### Evaluation Framework
The effectiveness of the attack methods was assessed using the BODEGA score, which considers both the success of the attack and the preservation of the text's original meaning. We applied these methods across five CA tasks: fact-checking, COVID-19 misinformation detection, propaganda detection, style-based news bias assessment, and rumor detection.

## Results
Our experiments demonstrated that GloTa significantly outperformed the baseline methods in propaganda detection and fact-checking, achieving the highest BODEGA scores. However, in style-based news bias assessment and rumor detection, GloTa's performance was comparable to the baselines, indicating a higher inherent robustness in classifiers for these tasks. When evaluated against a robust pre-trained RoBERTa classifier, GloTa still outperformed RoBERTa-ATTACK, albeit with lower overall success rates.

## Conclusion
Our study tested methods to challenge classification systems that assess text credibility. Our new approach, GloTa, outperformed existing techniques in detecting propaganda and fact-checking, revealing vulnerabilities in these areas. While a more robust AI system showed improved defense, it still had weaknesses. This research highlights the balance between creating effective attacks and maintaining text meaning, and demonstrates that identifying and replacing vulnerable words can effectively test AI credibility assessment systems. These findings advance our understanding of classification system vulnerabilities and pave the way for more reliable text analysis tools.

## Software
The code for our attack methods and the evaluation framework is available in the following files:
- `IncrediblAE_RoBERTa-ATTACK.ipynb`
- `IncrediblAE_GloTa.ipynb`

The software framework for evaluating our solutions is based on the notebook available at: [Evaluation Framework Notebook](https://colab.research.google.com/drive/1zxjwiztRLILFUjw5jR5xyL398bNSx8TI?usp=sharing).

The data used in the task can be accessed from the CheckThat! repository: [CheckThat! Repository](https://gitlab.com/checkthat_lab/clef2024-checkthat-lab/-/tree/main/task6?ref_type=heads), including a copy of the evaluation notebook: [Evaluation Notebook](https://gitlab.com/checkthat_lab/clef2024-checkthat-lab/-/blob/main/task6/IncrediblAE.ipynb?ref_type=heads).

## Hyperparameters

### RoBERTa-ATTACK
- **k**: 36
- **threshold_pred_score**: 0.3

### GloTa
- **max_candidates**: 30
- **max_substitutes**: 80
- **max_sub_rate**: 0.5
