# AI-Powered Student Answer Evaluation Using RAG Networks

This project implements an automated system for evaluating student answers using **Recurrent Attentional Graph Networks (RAG)**. It combines cutting-edge NLP techniques, including semantic similarity scoring and dynamic weighted evaluation metrics, to produce scores for student responses. The workflow and evaluation results are described in detail below.

---

## Questions and Answers
The questions and answers used in this project were sourced from [Deep Learning Questions & Answers for Data Scientists](https://github.com/youssefHosni/Data-Science-Interview-Questions-Answers/blob/main/Deep%20Learning%20Questions%20%26%20Answers%20for%20Data%20Scientists.md), ensuring relevance and diversity across topics.

The primary dataset used for this project is the **ASAG (Automated Short Answer Grading) Dataset**, which can be accessed at [ASAG Dataset GitHub Repository](https://github.com/DigiKlausur/ASAG-Dataset/tree/master). This dataset provides a robust foundation for evaluating subjective answers, containing student answers, reference answers, and associated scores.

---

## Workflow

1. **Dataset**: The dataset contains questions, student answers, and the corresponding textbook content from which the teacher answers are derived.
2. **RAG Application**: The questions are passed to the RAG model, which retrieves relevant content from the textbook and generates a teacher answer.
3. **Evaluation**:
   - The student answer is compared with the teacher answer.
   - A score is generated using dynamic weighted scoring based on semantic similarity and key phrase matching.

---

## Evaluation Results

1. **RAG Performance**:
   - The generated teacher answer is compared with a ground truth teacher answer (scraped from the web) using **BertScore** to assess how accurately RAG retrieves context and generates coherent responses.

2. **Student Answer Evaluation**:
   - **Preprocessing**:
     - Acronym expansion
     - Spelling correction
     - Coreference resolution
     - Sentence tokenization
   - **Processing**:
     - Sentence-wise semantic scoring
     - Extraction of immutable phrases (key phrases)
   - **Scoring**:
     - Dynamic weighted scoring combines semantic scores and phrase matches to produce a final score.

---

## Explanation of Files

1. **`QA.ipynb`**:  
   - The main pipeline notebook that executes the entire question-answer evaluation workflow, integrating RAG and evaluation metrics.

2. **`README.md`**:  
   - Documentation file detailing the project, its workflow, files, and evaluation methodology.

3. **`abbreviation_vocab.txt`**:  
   - Vocabulary file for expanding acronyms during preprocessing.

4. **`actual.txt`** and **`predicted.txt`**:  
   - Contain the actual (ground truth) and predicted scores for student answers, used for evaluation.

5. **`asag_classification.ipynb`**:  
   - Implements a classification model using neural networks to categorize student answers into predefined score levels.

6. **`asag_data_transformation.ipynb`**:  
   - Prepares the dataset by generating embeddings for student and reference answers using SentenceTransformer and combines them for analysis.

7. **`asag_dataset.csv`**:  
   - The original dataset containing questions, student answers, and reference answers, sourced from the [ASAG Dataset GitHub Repository](https://github.com/DigiKlausur/ASAG-Dataset/tree/master).

8. **`asag_regression.ipynb`**:  
   - Implements a regression model using neural networks to predict continuous scores for student answers.

9. **`cannyeval.py`**:  
   - Contains evaluation logic for comparing student answers and teacher answers using dynamic weighted scoring.

10. **`embedding_dataset.csv`**:  
    - Dataset containing concatenated embeddings of student and reference answers, used as input for the models.

11. **`open_source.ipynb`**:  
    - Notebook for scraping ground truth teacher answers from web sources to compare against RAG-generated answers.

12. **`predicted.txt`**:  
    - File storing the scores predicted by the models.

13. **`prediction.txt`**:  
    - Logs predictions made during the evaluation phase for further analysis.

14. **`questions.txt`**:  
    - Contains a list of questions used in the dataset.

15. **`requirements.txt`**:  
    - Lists all dependencies and Python libraries required to execute the project.

16. **`selected_asag_dataset.csv`**:  
    - Cleaned version of the original dataset with only the necessary columns: index, question, student_answer, grades_round, and ref_answer.

17. **`textbook.ipynb`**:  
    - Notebook for managing textbook content, which serves as the knowledge base for the RAG application.

18. **`textbook.txt`**:  
    - Textbook content used by the RAG model for retrieving context to generate teacher answers.

---
