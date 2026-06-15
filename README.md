# Aural-Trans---Real--Time-Multi---Speaker-Speech-transcription
Real-time multi-speaker speech transcription | Speaker Diarization | Sentiment Analysis | Text Summarization | Python | React.js
Aural Trans is an end-to-end speech intelligence system that goes beyond conventional transcription. It identifies multiple speakers in real time, analyzes the emotional tone of each speaker, and distills entire conversations into concise summaries — all through an intuitive web interface.

🛠️ Tech Stack

AI / ML

Whisper — Speaker diarization and speech-to-text
PyAnnote — Audio annotation and speaker segmentation
BERT — Sentiment analysis (Hugging Face Transformers)
T5 / GPT-3 — Abstractive text summarization
TensorFlow / PyTorch — Deep learning model training
Keras — Neural network architecture design
Librosa — Acoustic feature extraction (MFCCs, spectrograms)
Scikit-learn — Custom sentiment classification pipeline

Backend
Python — Core programming language
Flask — REST API and backend orchestration

Frontend
React.js — Interactive user interface
HTML5 / CSS3 / Bootstrap — Styling and layout
Redux — State management
WebSocket — Real-time updates
Axios — API communication

Audio Input (Upload / Microphone)
        │
        ▼
┌─────────────────────┐
│  Audio Preprocessing │  ← Librosa (noise reduction, normalization, MFCCs)
└─────────────────────┘
        │
        ▼
┌─────────────────────┐
│  Speaker Diarization │  ← Whisper + PyAnnote (real-time speaker separation)
└─────────────────────┘
        │
        ▼
┌──────────────────────────────────────────┐
│         Per-Speaker Processing           │
│  ┌─────────────────┐  ┌───────────────┐  │
│  │  Transcription  │  │   Sentiment   │  │
│  │   (ASR Model)   │  │ Analysis(BERT)│  │
│  └─────────────────┘  └───────────────┘  │
└──────────────────────────────────────────┘
        │
        ▼
┌─────────────────────┐
│   Text Summarization │  ← T5 Transformer (abstractive summaries)
└─────────────────────┘
        │
        ▼
┌─────────────────────┐
│   React.js Frontend  │  ← Real-time display of transcriptions,
│   (User Interface)   │     sentiment labels, and summaries
└─────────────────────┘
aural-trans/
├── README.md
├── requirements.txt
├── backend/
│   ├── app.py                  ← Flask API server
│   ├── aural_trans.py          ← Core pipeline orchestration
│   ├── audio_preprocessing.py  ← Librosa-based audio cleaning
│   ├── speaker_diarization.py  ← Whisper + PyAnnote integration
│   ├── sentiment_analysis.py   ← BERT-based sentiment classifier
│   └── text_summarization.py   ← T5 transformer summarizer
├── frontend/
│   ├── src/
│   │   ├── App.jsx             ← Main React component
│   │   ├── components/
│   │   │   ├── AudioUpload.jsx
│   │   │   ├── TranscriptionView.jsx
│   │   │   ├── SentimentPanel.jsx
│   │   │   └── SummaryView.jsx
│   └── public/
└── results/
    ├── output_transcription.png
    ├── sentiment_analysis.png
    ├── text_summarization.png
    └── speech_diarization.png

  Installation & setup 
  Prerequisites
  Python
  Node.js 16 +
  pip

Requirements
 tensorflow
torch
transformers
librosa
pyannote.audio
flask
flask-cors
scikit-learn
numpy
pandas
openai-whisper

Module 1 — Audio Preprocessing
Loads audio using Librosa
Applies noise reduction and pre-emphasis filtering
Normalizes audio levels
Extracts MFCCs, spectrograms, and prosodic features

Module 2 — Speaker Diarization
Uses Whisper (deep CNN-based) for speaker embedding generation
Uses PyAnnote for speaker segmentation and labeling
Handles overlapping speech and varying audio quality
Outputs speaker-labeled audio segments

Module 3 — Transcription & Sentiment Analysis
ASR models transcribe each speaker's audio segment
BERT-based models classify sentiment per segment
Integrates acoustic features (Librosa) with textual context for richer sentiment detection

Module 4 — Text Summarization
Transformer-based models (T5 / GPT-3) generate abstractive summaries
Sequence-to-sequence architecture with attention mechanisms
Captures key themes, sentiments, and speaker interactions

Module 5 — Frontend Interface

Real-time transcription display per speaker
Color-coded sentiment labels
Conversation summary panel
Audio file upload with progress indicator

Module 6 — Backend System

Flask REST API orchestrates all modules
Handles file upload, preprocessing, and pipeline coordination
Returns JSON with transcriptions, sentiments, and summary
The system underwent four levels of testing:

Testing:

White-Box Testing — Audio preprocessing validation, speaker turn identification, Whisper integration
Black-Box Testing — Sentiment classification accuracy, emotional nuance detection, cross-dataset consistency
User Interface Testing — Usability, navigation, real-time update verification
Integration Testing — Seamless data flow across all modules, speaker-specific summary accuracy

Future Enhancements
Fine-tuning BERT sentiment models on larger multilingual datasets
Integrating GPT-4 for richer abstractive summaries
Advanced noise cancellation for noisy environments
Real-time collaboration and multi-user support
Cloud deployment (AWS / Azure)
Multilingual transcription support
Multimodal analysis (facial expressions + speech)
Integration with Zoom, Teams, and Google Meet
