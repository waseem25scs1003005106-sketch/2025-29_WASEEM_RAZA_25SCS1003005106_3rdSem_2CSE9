[README.md](https://github.com/user-attachments/files/34855080/README.md)
# Handwritten Digit Recognizer: AI Internship at Codec Technologies

A small CNN that reads handwritten digits (0 to 9), built as my capstone project for the **1-Month Artificial Intelligence Internship** at **Codec Technologies Pvt. Ltd.**

| | |
|---|---|
| **Intern** | Waseem Raza |
| **Role** | Artificial Intelligence Intern |
| **Duration** | 03/08/2026 to 03/09/2026 (1 month, online) |
| **Approval** | AICTE & ICAC approved, National Internship Portal |
| **AICTE ID** | CORPORATE6759d549ce59e1733940553 |
| **Program Manager** | Dr. Anurag Shrivastava |

## About the internship

The program runs for four weeks:

| Week | Topics |
|---|---|
| 1 | AI, ML and DL overview, Python, NumPy, Pandas, data cleaning, Matplotlib and Seaborn |
| 2 | Linear and logistic regression with scikit-learn, accuracy / precision / recall / F1, cross-validation |
| 3 | Neural networks with TensorFlow and Keras, CNNs for image classification |
| 4 | NLP with NLTK and SpaCy, Q-learning basics, capstone project and presentation |

For the capstone I picked the image classification option and built a digit recognizer.

## The project

**Problem:** given a 28x28 grayscale image of a handwritten digit, predict which digit (0 to 9) it is.

**Dataset:** [MNIST](https://en.wikipedia.org/wiki/MNIST_database), 60,000 training images and 10,000 test images. It downloads automatically through Keras the first time the script runs.

**Approach:**

1. Scale pixel values from 0-255 to 0-1 and add a channel dimension.
2. Train a CNN with two convolution + max-pooling blocks, a dropout layer and a 10-way softmax output.
3. Use 10% of the training data for validation while training, then evaluate once on the untouched test set.

**Model**

```
Input (28, 28, 1)
Conv2D 32 filters, 3x3, ReLU
MaxPooling 2x2
Conv2D 64 filters, 3x3, ReLU
MaxPooling 2x2
Flatten
Dropout 0.5
Dense 10, softmax
```

About 34,800 trainable parameters. Optimizer: Adam. Loss: sparse categorical cross-entropy. Defaults: 10 epochs, batch size 128.

## Results

> Run the script once and copy your numbers here, then delete this note. The script writes everything to `results/`.

| Metric | Value |
|---|---|
| Test accuracy | [xx.xx %] |
| Test loss | [x.xxxx] |
| Epochs / batch size | 10 / 128 |

Charts saved by the script:

![Training curves](results/training_curves.png)
![Confusion matrix](results/confusion_matrix.png)
![Sample predictions](results/sample_predictions.png)

## How to run

**Option 1: Google Colab (easiest, no setup)**

1. Open [colab.research.google.com](https://colab.research.google.com) and create a new notebook.
2. Upload `digit_recognizer.py`, or clone this repo in a cell with `!git clone <your repo link>`.
3. Run `!python digit_recognizer.py`.

**Option 2: on your own computer**

```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
python -m venv venv
source venv/bin/activate        # on Windows: venv\Scripts\activate
pip install -r requirements.txt
python digit_recognizer.py
```

Use `--epochs 15` to train longer. Training takes a few minutes on a normal CPU.

## Repo contents

```
.
├── README.md
├── digit_recognizer WASEEM RAZA.py       # data loading, model, training, evaluation, charts
├── requirements WASEEM RAZA.txt
├── results/                  # model, metrics and charts appear here after a run
└── docs/                     # internship report, presentation and certificate
```

## Tools used

Python, TensorFlow, Keras, NumPy, scikit-learn, Matplotlib, Seaborn, Git and GitHub.

## What I learned

- How an image goes from raw pixels to a prediction through convolution, pooling and a classifier layer
- Why scaling the data and holding out a test set matter
- Reading a confusion matrix to see which digits the model mixes up
- Packaging a project so someone else can run it with a few commands

## Contact

Waseem Raza, [waseem.25scs1003005106@iilm.edu]
