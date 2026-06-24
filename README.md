# NGrams-for-Mathematical-Series
# N-Grams on Numerical Data: A Fibonacci Experiment 🔢

A small experiment exploring whether **N-gram models**, commonly used in Natural Language Processing (NLP), can be applied to **numerical sequences** instead of text.

Rather than predicting the next word in a sentence, this project attempts to predict the next number in the **Fibonacci sequence** using N-gram patterns.

## Motivation

When learning about N-grams, they're almost always presented in the context of language:

```text
I love machine learning
```

Bigrams:

```text
(I, love)
(love, machine)
(machine, learning)
```

But N-grams aren't inherently tied to language.

At their core, they are simply a way of modeling **sequences**.

This project explores a simple question:

> If words can be treated as tokens, can numbers be treated as tokens too?

To investigate this, I used the Fibonacci sequence as a test case.

---

## What You'll Learn

This notebook demonstrates:

* How N-grams work internally
* Building N-grams from numerical sequences
* Sliding window sequence generation
* Pattern-based prediction
* The difference between memorization and understanding
* Why traditional N-grams eventually hit limitations

---

## Example

Fibonacci Sequence:

```text
0, 1, 1, 2, 3, 5, 8, 13, 21, 34
```

### Bigrams

```text
(0,1)
(1,1)
(1,2)
(2,3)
(3,5)
```

### Trigrams

```text
(0,1,1)
(1,1,2)
(1,2,3)
(2,3,5)
(3,5,8)
```

The model then uses previously observed patterns to predict future values.

---

## Project Structure

```text
.
├── NGrams_Fibonacci.ipynb
├── README.md
└── assets/
    ├── demo.gif
    └── screenshots/
```

---

## How It Works

### 1. Generate Fibonacci Numbers

Create a Fibonacci sequence of arbitrary length.

```python
def fibonacci(n):
    ...
```

### 2. Create N-Grams

Transform the sequence into fixed-length windows.

```python
make_ngrams(sequence, n)
```

Example:

```text
[1, 2, 3, 5, 8]

↓

(1,2,3)
(2,3,5)
(3,5,8)
```

### 3. Predict the Next Value

Using previously observed N-grams, the notebook attempts to predict the next number in the sequence.

---

## Interactive Visualization

One of the most interesting parts of this project is visualizing the sliding N-gram window.

Example:

```text
[0,1,1]
   [1,1,2]
      [1,2,3]
         [2,3,5]
            [3,5,8]
```

Watching the window move across the sequence makes it much easier to understand how N-gram-based models learn context.

### Demo

Add your GIF here:

```markdown
![N-Gram Visualization](assets/demo.gif)
```

---

## Key Insight

The experiment revealed an important distinction:

### N-Grams Can Learn Patterns

They can successfully capture recurring sequences and make predictions based on previously observed data.

### N-Grams Cannot Learn Rules

The model recognizes:

```text
(13,21) → 34
```

But it does not understand:

```text
next = previous + current
```

It memorizes observations rather than learning the underlying mathematical relationship.

This limitation is one reason modern sequence models evolved beyond traditional N-grams.

---

## Why This Matters

Although this project uses Fibonacci numbers, the same idea can be extended to:

* Time-series forecasting
* Sensor data
* Stock prices
* DNA sequences
* User behavior analytics
* Event streams

Anywhere there is an ordered sequence, N-grams can be applied.

---

## Running the Notebook

Clone the repository:

```bash
git clone https://github.com/yourusername/ngrams-fibonacci.git
cd ngrams-fibonacci
```

Install dependencies:

```bash
pip install notebook
```

Launch Jupyter:

```bash
jupyter notebook
```

Open:

```text
NGrams_Fibonacci.ipynb
```

---

## Future Ideas

Some interesting extensions include:

* Applying N-grams to Prime Numbers
* Pascal's Triangle
* Time-series forecasting datasets
* Markov Chain comparison
* Probability-based N-gram prediction
* Comparing N-grams with RNNs and Transformers

---

## Related Blog Post

I also wrote a detailed breakdown of this experiment explaining the intuition behind numerical N-grams, sequence prediction, and what this teaches us about language models.

📖 Link: *Add your Hashnode article here*

---

## Contributing

Feel free to fork the repository, experiment with different numerical sequences, and submit improvements.

If you build something interesting using this idea, I'd love to see it.

---
## 📖 Read the Full Story

This repository accompanies a blog post where I explored a simple but interesting question:

> Can N-grams, traditionally used in NLP, be applied to numerical sequences like Fibonacci numbers?

In the article, I walk through:

* What N-grams are
* How they work on numerical data
* Building Fibonacci N-grams step-by-step
* Sequence prediction using sliding windows
* The limitations of N-gram-based learning
* Why modern language models evolved beyond N-grams

🔗 **Hashnode Article:** [Add Your Blog Link Here]

If you're interested in the intuition behind the code rather than just the implementation, the blog post is a great place to start.

---
### A Simple Question Started This Project

> Can N-grams understand numbers the same way they understand words?

The answer is surprisingly interesting.

Sometimes understanding AI starts not with billion-parameter models, but with:

```text
0, 1, 1, 2, 3, 5, 8...
```
