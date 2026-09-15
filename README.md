# WordPiece Tokenization

A simple Python implementation of WordPiece Tokenization using a small custom vocabulary.

## Overview

WordPiece Tokenization breaks words into smaller subword tokens.

In this project, we use the following words:

```text
high
higher
highest
```

The tokenizer produces:

```text
high     → ['high']
higher   → ['high', 'er']
highest  → ['high', 'est']
```

The tokens are then converted into numerical IDs.

## Project Structure

```text
WordPiece/
│
├── corpus.txt
├── wordpiece.py
└── README.md
```

## corpus.txt

The `corpus.txt` file contains the words used for tokenization:

```text
high
higher
highest
```

## wordpiece.py

The Python program:

1. Reads the corpus.
2. Defines a vocabulary.
3. Finds the longest matching subword.
4. Splits words into tokens.
5. Converts tokens into IDs.
6. Displays the final result.

## Vocabulary

The vocabulary used in this demonstration is:

```python
vocab = {
    "[PAD]": 0,
    "[UNK]": 1,
    "[CLS]": 2,
    "[SEP]": 3,
    "high": 4,
    "er": 5,
    "est": 6
}
```

## Tokenization

| Word    | Tokens            | IDs      |
| ------- | ----------------- | -------- |
| high    | `['high']`        | `[4]`    |
| higher  | `['high', 'er']`  | `[4, 5]` |
| highest | `['high', 'est']` | `[4, 6]` |

## How to Run

Open Command Prompt in the project folder.

Check the Python version:

```cmd
python --version
```

Run the program:

```cmd
python wordpiece.py
```

## Expected Output

```text
Word: high
Tokens: ['high']
IDs: [4]

Word: higher
Tokens: ['high', 'er']
IDs: [4, 5]

Word: highest
Tokens: ['high', 'est']
IDs: [4, 6]
```

## How It Works

The tokenizer searches for the longest vocabulary piece that matches the current part of the word.

For example:

```text
higher
  ↓
high + er
  ↓
['high', 'er']
  ↓
[4, 5]
```

Similarly:

```text
highest
  ↓
high + est
  ↓
['high', 'est']
  ↓
[4, 6]
```

## Purpose

This project demonstrates the basic idea of subword tokenization and how tokens can be converted into numerical IDs for use by NLP models.

## Requirements

* Python 3.x
* No external Python libraries are required.

The project uses Python's built-in `collections.Counter`.

## Author

WordPiece Tokenization Mini Project
