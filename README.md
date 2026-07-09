# AI-Powered Earnings Call Analysis Using an End-to-End AI Pipeline

An end-to-end AI pipeline that transforms raw earnings call audio into structured business insights using modern Speech Processing and Natural Language Processing (NLP) techniques.

Developed as part of the **SeqHub AI Research Hackathon**.

---

# Project Overview

Earnings calls provide valuable information about a company's financial performance, business strategy, future outlook, and market position. However, manually reviewing lengthy recordings can be both time-consuming and inefficient.

This project automates the analysis process by building a modular AI pipeline that:

- Converts speech into text
- Identifies who is speaking throughout the conversation
- Detects the major discussion topics
- Identifies where discussions change from one topic to another
- Analyzes the sentiment expressed by each speaker
- Exports all results into a structured JSON format

The project demonstrates how multiple AI models can be integrated into a single workflow to transform unstructured earnings call audio into meaningful business insights.

---

# Project Highlights

- End-to-end AI pipeline for earnings call analysis
- Modular implementation with five independent processing stages
- Speaker diarization using Pyannote Audio
- Topic segmentation using BERTopic
- Transformer-based sentiment analysis
- Word Error Rate (WER) evaluation
- Structured JSON export
- Results visualized using Matplotlib

---

# Project Objective

The objective of this project is to design and implement an automated AI pipeline capable of analyzing earnings call recordings.

The pipeline performs five major tasks:

- **Transcription** – Convert speech into text using Faster-Whisper.
- **Speaker Diarization** – Identify and separate different speakers using Pyannote Audio.
- **Topic Segmentation** – Discover the major discussion topics using BERTopic.
- **Boundary Detection** – Detect where conversations shift between topics.
- **Sentiment Analysis** – Determine the emotional tone of each speaker turn using a transformer-based model.

The final output is exported as a structured JSON file for downstream analysis.

---

# System Architecture

```text
                     Earnings Call Audio
                              │
                              ▼
                   Faster-Whisper
                    (Transcription)
                              │
                              ▼
                    Pyannote Audio
                 (Speaker Diarization)
                              │
                              ▼
                       BERTopic
                  (Topic Segmentation)
                              │
                              ▼
                  Boundary Detection
                              │
                              ▼
          Transformer Sentiment Analysis
                              │
                              ▼
                    Structured JSON Output
```

---

# Technologies Used

| Technology | Purpose |
|------------|---------|
| Python | Core programming language |
| Faster-Whisper | Speech transcription |
| Pyannote Audio | Speaker diarization |
| BERTopic | Topic segmentation |
| Sentence-Transformers | Text embeddings |
| Hugging Face Transformers | Sentiment analysis |
| Scikit-learn | Stop-word filtered keyword extraction |
| Matplotlib | Data visualization |
| JiWER | Word Error Rate (WER) evaluation |
| JSON | Structured output format |
| Google Colab | Development environment |

---

# Repository Structure

```text
GitHub Repository
│
├── README.md
│
├── Audio_Intelligence_Pipeline.ipynb
│
├── System_Design_Report.docx
│
├── pipeline_output.json
│
└── assets/
      ├── speaker_distribution.png
      ├── topic_distribution.png
      └── sentiment_distribution.png
```

---

# Installation

To run this project on your own machine, first download the repository from GitHub.

Clone the repository:

```bash
git clone https://github.com/yourusername/your-repository-name.git
```

Move into the project folder:

```bash
cd your-repository-name
```

Install the required libraries:

```bash
pip install faster-whisper pyannote.audio transformers sentencepiece
pip install bertopic sentence-transformers
pip install jiwer matplotlib
```

---

# Usage

1. Open the notebook in **Google Colab**.
2. Run the install cells, then restart the runtime if prompted.
3. Authenticate with your Hugging Face access token (required for the diarization model).
4. Mount Google Drive and upload the earnings call audio file.
5. Run each notebook section sequentially, following the module headers.
6. Review the generated visualizations and JSON output.

---

# Results

The completed pipeline successfully performs:

- ✅ Speech Transcription
- ✅ Speaker Diarization
- ✅ Topic Segmentation
- ✅ Boundary Detection
- ✅ Sentiment Analysis
- ✅ Word Error Rate (WER) Evaluation
- ✅ Structured JSON Export

### Performance Summary

| Stage | Result |
|--------|--------|
| Transcription | 60 timestamped transcript segments |
| Speaker Diarization | 4 speakers identified |
| Speaker Turns | 17 merged speaker turns |
| Topic Segmentation | 3 discussion topics detected |
| Boundary Detection | 11 topic boundaries identified |
| Sentiment Analysis | Positive and Neutral predictions (no negative turns detected in this test call) |
| Word Error Rate | **9.6%** |

---

# Visualizations

The notebook includes three visualizations, also available in `assets/`:

-  **Speaker Distribution** — number of turns per speaker
-  **Topic Distribution** — timeline of which topic was discussed when
- **Sentiment Distribution** — overall emotional tone breakdown

These visualizations provide an intuitive overview of speaker participation, discussion themes, and the overall emotional tone of the earnings call.

---

# Challenges Encountered

Some of the key challenges encountered during development included:

- Managing recurring dependency conflicts (NumPy, PyTorch, Torchaudio, Pyannote Audio) in Google Colab
- Handling GPU usage limits during experimentation
- Improving topic quality by merging transcript fragments into full speaker turns and filtering stop words
- Correcting under-detected speakers (3 vs. 4) using the known speaker count

---

# Future Improvements

Possible future enhancements include:

- Using larger Whisper models for improved transcription accuracy
- Adding additional evaluation metrics (DER, NMI, C_v, WindowDiff, and Pk)
- Supporting multilingual earnings calls
- Building an interactive dashboard for result exploration
- Supporting real-time earnings call analysis

---

# Tools & Libraries Referenced

- Faster-Whisper
- Pyannote Audio
- BERTopic
- Hugging Face Transformers
- Sentence-Transformers
- JiWER
- Scikit-learn
- Matplotlib

---

# Author

**Joy Abiodun**

AI Applications & Content Development Intern

SeqHub Analytics
