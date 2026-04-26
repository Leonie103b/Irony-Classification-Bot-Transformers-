# Irony-Classification-Bot-Transformers-

A simple interactive CLI “bot” built with Transformers that loads a selected text-classification model and repeatedly classifies user-entered sentences as **irony** or **Unirony**.

## Features
- Loads **different Hugging Face Transformers models** (choose from a list or configure via argument/env).
- Runs in a **loop**: you can enter multiple sentences without restarting.
- Outputs a label for each sentence:
  - `Irony`
  - `Unirony`
- Optional: shows confidence scores (if enabled).

## How it works (high level)
1. The program loads a Hugging Face `AutoTokenizer` and `AutoModelForSequenceClassification` (or a `pipeline("text-classification")`).
2. The user types a sentence in the terminal.
3. The model predicts the class (irony vs non-irony).
4. The program prints the predicted label (and optionally probability/score).
5. Steps 2–4 repeat until the user exits (e.g., typing `bye`).

## Requirements

```bash
pip install -r environment.yml
```

## Usage

### Select a model (examples)
Change the configured models in code, document the available options here:
#loading the model

model_name = "xxxxx"

## Example session
```text
What is the emotion in the sentence?(bye for quit)：  Feeling good.
The emotion is： Unirony
What is the emotion in the sentence?(bye for quit)：  I hate plane rides but I wanna go to so many different countries
The emotion is： Irony

> exit
Bye!
```

## Project structure
- `bot.ipynb` — interactive loop and inference
- `environment.yml` — dependencies

## Notes
- Prediction quality depends on the chosen model and its training data.
- If you see label names like `label_map`, you may map them to `IRONY` / `UNIRONY` in code and document that mapping here.
