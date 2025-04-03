# Do LLMs Overcome Shortcut Learning? An Evaluation of Shortcut Challenges in Large Language Models

> **Abstract:** Large Language Models (LLMs) have shown remarkable capabilities in various natural language processing tasks. However, LLMs may rely on dataset biases as shortcuts for prediction, which can significantly impair their robustness and generalization capabilities. This paper presents Shortcut Suite, a comprehensive test suite designed to evaluate the impact of shortcuts on LLMs' performance,  incorporating six shortcut types, five evaluation metrics, and four prompting strategies. Our extensive experiments yield several key findings: 1) LLMs demonstrate varying reliance on shortcuts for downstream tasks, significantly impairing their performance. 2) Larger LLMs are more likely to utilize shortcuts under zero-shot and few-shot in-context learning prompts. 3) Chain-of-thought prompting notably reduces shortcut reliance and outperforms other prompting strategies, while few-shot prompts generally underperform compared to zero-shot prompts. 4) LLMs often exhibit overconfidence in their predictions, especially when dealing with datasets that contain shortcuts.  5) LLMs generally have a lower explanation quality in shortcut-laden datasets, with errors falling into three types: distraction, disguised comprehension, and logical fallacy. Our findings offer new insights for evaluating robustness and generalization in LLMs and suggest potential directions for mitigating the reliance on shortcuts. 

The repository contains the code and dataset for  "[Do LLMs Overcome Shortcut Learning? An Evaluation of Shortcut Challenges in Large Language Models](https://arxiv.org/abs/2410.13343)".  This work is published at EMNLP 2024.



## Dataset Overview

**ShortcutSuite** is constructed to systematically assess the susceptibility of LLMs to six types of shortcut, as detailed in the paper. It is primarily based on two NLI datasets: [MultiNLI](https://arxiv.org/pdf/1704.05426) and [HANs](https://arxiv.org/abs/1902.01007) , with additional modifications for specific shortcut types.

### Structure

```bash
└── dataset 
    ├── dev_matched.tsv                  # Standard
    ├── dev_matched_negation.tsv         # Negation
    ├── dev_matched_position.tsv         # Position
    ├── dev_matched_style_bible.tsv      # Style
    ├── lexical_overlap.tsv              # Lexical Overlap
    ├── subsequence.tsv                  # Subsequence
    ├── constituent.tsv                  # Constituent
```

### Descriptions

- **Standard**: A balanced subset of 3,000 examples from the MultiNLI development set, covering all three labels and ten genres.
- **Lexical Overlap, Subsequence, Constituent**: 3,000 examples each from the HANS dataset, targeting structural heuristics with balanced label and template distribution.
- **Negation**: Hypotheses in the Standard set are appended with randomly selected tautological negation phrases to test models' sensitivity to strong negations.
- **Position**: Tautological phrases are inserted at varying positions in the hypothesis to evaluate whether models rely on positional cues.
- **Style**: Premises in the Standard set are transferred into Bible-style text using the [STRAP](https://arxiv.org/pdf/2010.05700) model, testing whether stylistic features influence model predictions.

ShortcutSuite enables fine-grained and interpretable evaluation of LLMs under shortcut challenges.



## Citation

If you find this work useful, please cite our paper:

```
@inproceedings{yuan2024llms,
  title={Do LLMs Overcome Shortcut Learning? An Evaluation of Shortcut Challenges in Large Language Models},
  author={Yuan, Yu and Zhao, Lili and Zhang, Kai and Zheng, Guangting and Liu, Qi},
  booktitle={Proceedings of the 2024 Conference on Empirical Methods in Natural Language Processing},
  pages={12188--12200},
  year={2024},
  url = "https://arxiv.org/abs/2410.13343"
}
```
