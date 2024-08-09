# Natural Dialogue Generation between Speakers using Large Language Models

**Author:** Shubhabrata  
**Date:** August 1, 2024  

## ![#3cb371](https://via.placeholder.com/15/3cb371/000000?text=+) Introduction
This project focuses on fine-tuning a pre-trained Language Learning Model (LLM) to generate dialogues between two speakers. The primary goal is to enhance the LLM’s ability to produce coherent and contextually appropriate conversations. The project involves several stages, including Exploratory Data Analysis (EDA), model selection, fine-tuning, and evaluation. This README provides a detailed step-by-step description of the methodology, specific choices, and parameters defined during the project.

## ![#4682b4](https://via.placeholder.com/15/4682b4/000000?text=+) Project Steps

### ![#ff6347](https://via.placeholder.com/15/ff6347/000000?text=+) Step 1: Exploratory Data Analysis (EDA)

#### Data Collection and Preparation
The data for this project was sourced from two CSV files hosted on Google Drive. The files contain dialogues between Lex Fridman and two different speakers, Lee Cronin and Lisa Randall.

- **Downloading Data:** The files were downloaded using the PyDrive library.
- **Reading Data:** The downloaded files were read into Pandas DataFrames for further analysis.

#### Data Analysis
The data was analyzed to understand its structure and content.

- **Missing Values:** Checked for missing values.
- **Text Length Distribution:** Analyzed text lengths to understand variability.
- **Common Words Analysis:** Identified common words using word frequency analysis.
- **Speaker Distribution:** Analyzed the distribution of speakers.

### ![#ff6347](https://via.placeholder.com/15/ff6347/000000?text=+) Step 2: Model Selection
Several pre-trained models were considered:

- **GPT-2:** Known for general text generation.
- **DialoGPT:** Specifically designed for dialogue generation.
- **BlenderBot:** A conversational model by Facebook.
- **GPT-Neo:** A large-scale model by EleutherAI.

### ![#ff6347](https://via.placeholder.com/15/ff6347/000000?text=+) Step 3: Fine-Tuning the Pre-Trained LLM

#### Tokenization
Text data was tokenized using respective tokenizers.

#### Training Parameters
Parameters such as learning rate, batch size, and number of epochs were defined.

#### Training Process
Models were trained using supervised and reinforcement learning techniques.

### ![#ff6347](https://via.placeholder.com/15/ff6347/000000?text=+) Step 4: **Minimizing Forgetfulness with Elastic Weight Consolidation (EWC)**

In this project, **Elastic Weight Consolidation (EWC)** was employed to mitigate the issue of catastrophic forgetting. EWC plays a crucial role in retaining knowledge from previously learned tasks while fine-tuning the model on new data. By adding a regularization term to the loss function, EWC helps in preserving important weights that are critical for the previously learned tasks.

For a deeper understanding of EWC, you can refer to the original paper by Kirkpatrick et al. titled ["Overcoming catastrophic forgetting in neural networks"](https://arxiv.org/abs/1612.00796).

#### Continual Learning
EWC was specifically applied during the fine-tuning process to ensure that the model did not lose its ability to generate coherent dialogues from the original dataset, even as it was being trained on new data.

#### Evaluation Metrics
Metrics such as perplexity and BLEU score were used to evaluate performance.

### ![#ff6347](https://via.placeholder.com/15/ff6347/000000?text=+) Step 5: Model Testing and Evaluation

#### Initial Prompt
A predefined prompt was used for dialogue generation.

#### Response Generation
Models generated responses based on the initial prompt and subsequent exchanges.

#### Evaluation
Generated dialogues were evaluated for coherence and relevance.

**Findings:**

- **BlenderBot:** Performed the best, generating relevant and coherent dialogues.
- **GPT-Neo:** Introduced unrelated information in the generated dialogues.

**Conclusion:**  
BlenderBot is the most suitable model for generating coherent dialogues. Future work may explore additional fine-tuning techniques.

## ![#4682b4](https://via.placeholder.com/15/4682b4/000000?text=+) Benchmarking Results

### Evaluation Results
The results of the initial test data evaluation are as follows:

| Metric           | Old Model | New Model |
|------------------|-----------|-----------|
| **BLEU Score**   | 0.00499987 | 0.0073136 |
| **Perplexity Score** | 4.2378   | 71.3368   |

## ![#4682b4](https://via.placeholder.com/15/4682b4/000000?text=+) Discussion

### BLEU Score Analysis
Both models exhibit low BLEU scores. The new model shows a slightly higher BLEU score, suggesting a marginal improvement.

### Perplexity Analysis
The new model has a higher perplexity score, indicating less coherence or more prediction challenge.

## ![#4682b4](https://via.placeholder.com/15/4682b4/000000?text=+) Recommendations
- **Manage Input Length:** Implement truncation or splitting strategies.
- **Model Tuning:** Adjust hyperparameters or training data.

## ![#4682b4](https://via.placeholder.com/15/4682b4/000000?text=+) Conclusion
This report provides insights into the performance of the fine-tuned language models. Despite warnings and low BLEU scores, the analysis offers a foundation for further improvements.
