# Car Review Analysis with Hugging Face Transformers

This project demonstrates various **Natural Language Processing (NLP)** tasks on a dataset of car reviews using the powerful **Hugging Face Transformers library**. It covers sentiment analysis, translation, question answering, and summarization, providing insights into customer feedback.

---

## Project Overview

The core of this project lies in leveraging pre-trained models from the **Hugging Face ecosystem** to perform complex NLP tasks with relatively little code. We explore different applications of transformer models, from classifying review sentiment to extracting specific information and generating concise summaries.

---

## Key Features

* **Sentiment Analysis:** Determine the emotional tone (positive/negative) of car reviews.
* **Text Translation:** Translate review snippets from English to Spanish.
* **Question Answering:** Extract answers to specific questions directly from review text.
* **Text Summarization:** Condense lengthy reviews into shorter, coherent summaries.

---

## Technical Details and Method Choices

### Data

The project utilizes a CSV file named `car_reviews.csv` which contains car review texts and their corresponding sentiment labels. A separate `reference_translations.txt` file is used to provide ground truth for translation evaluation.

### Hugging Face `pipeline`

The **Hugging Face `pipeline` API** is the cornerstone of this project. It was chosen for its **simplicity and efficiency**. The `pipeline` abstracts away the complexities of tokenization, model loading, and inference, allowing for quick experimentation and deployment of various NLP tasks. This approach significantly reduces the amount of boilerplate code required, making the project more readable and maintainable.

### Model Selection

For each task, specific pre-trained models were chosen for their suitability and general performance:

* **Sentiment Analysis:** The default sentiment analysis model provided by the `pipeline` was used. This model is generally robust and performs well on a wide range of sentiment classification tasks.
* **Translation (English to Spanish):** The `Helsinki-NLP/opus-mt-en-es` model was selected. This model is part of the **OPUS-MT project**, known for its high-quality machine translation capabilities across many language pairs, making it a reliable choice for English-Spanish translation.
* **Question Answering:** The `deepset/minilm-uncased-squad2` model was employed. This model is fine-tuned on the **SQuAD 2.0 dataset**, a benchmark for question answering, ensuring its ability to extract answers from given contexts accurately.
* **Summarization:** The default summarization model provided by the `pipeline` was utilized. These models are typically powerful sequence-to-sequence models that can generate concise and coherent summaries while retaining the main points of the original text.

### Evaluation Metrics

To assess the performance of the models, standard NLP evaluation metrics from the **Hugging Face `evaluate` library** were used:

* **Accuracy and F1-score:** These metrics were chosen to evaluate the **classification performance of the sentiment analysis model**. Accuracy provides a general measure of correctness, while the F1-score offers a balance between precision and recall, which is particularly important for imbalanced datasets or when both false positives and false negatives are costly.
* **BLEU Score:** This metric was used to evaluate the **quality of the machine translation**. BLEU (Bilingual Evaluation Understudy) compares the similarity between machine-translated text and a set of human-translated reference texts, providing a widely accepted measure of translation fluency and adequacy.
