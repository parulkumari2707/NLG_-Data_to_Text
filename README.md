# NLG_-Data_to_Text

## Overview
This repository contains a Jupyter notebook (`NLG_data_to_text_webNLG.ipynb`) designed to handle Natural Language Generation (NLG) tasks using the WebNLG dataset. The notebook focuses on transforming structured data (triples) into coherent textual descriptions with the help of the T5 transformer model.

## Key Features
1. **Dataset Loading and Exploration**:
   - The notebook loads the WebNLG dataset (`webNLG2020_train.csv`) using pandas.
   - Provides a preview of dataset columns: `prefix`, `input_text`, and `target_text`.
   - `input_text`: Encodes triples in the form of `Entity | Relation | Value`.
   - `target_text`: Corresponding natural language description of the triples.

2. **Model Fine-tuning**:
   - Implements T5 (`Text-To-Text Transfer Transformer`) for sequence-to-sequence tasks.
   - Utilizes `T5Tokenizer` and `T5ForConditionalGeneration` from the `transformers` library.

3. **Data Preparation**:
   - Prepares the input and target text for model training by tokenizing the sequences.
   - Demonstrates techniques for managing input and output length constraints for the T5 model.

4. **Training and Evaluation**:
   - Fine-tunes the pre-trained T5 model on the WebNLG dataset.
   - Evaluates the model using generated text and compares it against the target descriptions.

## How to Use
1. **Setup**:
   - Ensure Python 3.x is installed.
   - Install required libraries: `transformers`, `pandas`, `torch`.
     ```bash
     pip install transformers pandas torch
     ```

2. **Run the Notebook**:
   - Open the notebook in Jupyter or any compatible editor.
   - Execute cells sequentially to preprocess data, fine-tune the model, and generate text.

3. **Input Data Format**:
   - The dataset must include:
     - `input_text`: Structured triples (e.g., `Entity | Relation | Value`).
     - `target_text`: Textual representation of the triples.
   - Example:
     | input_text       | target_text                  |
     |------------------|-----------------------------|
     | Paris | IsCapitalOf | France | Paris is the capital of France. |

4. **Model Fine-tuning**:
   - The notebook demonstrates loading a pre-trained T5 model and fine-tuning it for the NLG task.

5. **Generate Predictions**:
   - Once trained, the model can generate natural language descriptions for new triples provided as input.

## Dependencies
- Python 3.x
- Transformers library
- Pandas
- PyTorch

## Example Output
### Input:
```
City | LocatedIn | Country
```
### Output:
```
The city is located in the country.
```

## License
This project is released under the MIT License.
