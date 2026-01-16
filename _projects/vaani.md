---
name: vaani
title: "Vaani: Agentic Hindi Audiobook Creator"
brief_description: "Automatically converting Hindi books into high-quality audiobooks using voice cloning and emotion-aware synthesis"
status: Active
affiliation: "GAIR Lab × Skillplot @ BITS Pilani"
disciplines:
  - "Computer Science / AI & Machine Learning"
  - "Signal Processing / Audio Engineering"
  - "Software Engineering / Audio Systems"
---

## Project Overview

Current Text-to-Speech tools often sound robotic, especially for Hindi literature, which requires **emotion and specific reciting styles**. 

**Project Vaani** aims to build a software tool that **automatically converts Hindi books (PDF/Text) into high-quality audiobooks** using a specific author's voice. The core engineering challenge is **Voice Cloning** and **Emotion Control**—you will build a system where an AI agent reads the text, decides if a sentence should be spoken with anger, sadness, or joy, and then generates the audio using a cloned voice model.

This is a unique opportunity to work on **underrepresented language AI**—most voice synthesis research focuses on English. Your work will have direct impact in making Hindi literature more accessible.

## Expected Outcomes

### Comparative Study Report
**"Open Source vs. Commercial Voice Cloning for Hindi"**—a technical report benchmarking different voice synthesis approaches on Hindi pronunciation, emotional range, speed, and cost.

### Working Python Application
A functional application that generates an audiobook chapter from a PDF, including:
- Text extraction and preprocessing
- Emotion detection & tagging
- Voice synthesis
- Audio assembly and quality checks

### Fine-Tuned Voice Model
A fine-tuned open-source voice model capable of mimicking a target author's voice characteristics.

### Browser-Based Interface
A simple Streamlit or React dashboard allowing users to upload PDFs, set emotion parameters, and download generated audiobooks.

## Key Engineering Modules

### 1. Technology Evaluation (The Experiment)

A key part of this internship is the **"Build vs. Buy" evaluation**. You will set up two parallel pipelines to test voice cloning quality for Hindi:

**Pipeline A (Open Source):**
- Deploy models like **F5-TTS** (excellent for zero-shot cloning)
- Coqui **XTTS-v2** (strong multilingual support)
- **Kokoro** (lightweight/fast)

**Pipeline B (Commercial APIs):**
- **ElevenLabs** (industry standard for emotion)
- **Azure AI Speech** (enterprise-grade)

**Goal:** Produce a technical report comparing them on:
- Hindi pronunciation accuracy
- Emotional range and nuance
- Processing speed
- Cost per hour of audio

### 2. Intelligent Script Processing (The Logic)

Build a Python backend where an **LLM (like Llama 3)** analyzes the Hindi text before audio generation. The LLM will insert **"direction tags"** into the text:

```
Original: "राहुल को गुस्सा आ गया"
Tagged: "[Tone: Angry, Intensity: High] राहुल को गुस्सा आ गया"

Original: "वह अकेले बैठा था"
Tagged: "[Tone: Melancholic, Pause: 2s] वह अकेले बैठा था"
```

These tags guide the voice generation system.

### 3. Audio Synthesis Pipeline (The Engine)

Develop the code that:
- Takes the tagged text and author's reference audio sample
- Generates speech using the cloned voice model
- Implements **Forced Alignment** (using OpenAI Whisper) to ensure generated audio matches text perfectly
- Removes hallucinations or skipped words

### 4. Web Application (The Interface)

Create a simple dashboard where users can:
- Upload a Hindi PDF and MP3 author sample
- View and edit emotion tags manually
- Generate audiobook chapters
- Download final audio files
- (Optional) Track generation history

## Technical Architecture

```
Hindi PDF/Text Input
        ↓
Text Extraction & Preprocessing
        ↓
Emotion Detection (via LLM)
        ↓
Voice Synthesis Pipeline
   (F5-TTS / XTTS-v2 / ElevenLabs)
        ↓
Forced Alignment (Whisper)
        ↓
Audio Quality Check
        ↓
Audiobook Output (.mp3 / .wav)
```

## Research Focus

- **Voice Cloning for Low-Resource Languages:** How well can SOTA models clone Hindi voices?
- **Emotion in Speech Synthesis:** Can we programmatically inject emotion into generated speech?
- **Open vs. Proprietary:** What are the trade-offs between open-source and commercial solutions?
- **Forced Alignment:** How to ensure generated audio perfectly matches transcribed text?

## Project Deliverables

1. ✅ Two parallel voice synthesis pipelines (open-source + commercial)
2. ✅ Emotion tagging system using LLM
3. ✅ Fine-tuned voice model for target author
4. ✅ Forced alignment module using Whisper
5. ✅ Web application (Streamlit or React)
6. ✅ Comparative technical report
7. ✅ Open-source code repository with setup guide
8. ✅ Sample audiobook output demonstrating quality

## Technology Stack

- **Language:** Python (core), JavaScript/React (UI)
- **Voice Models:** F5-TTS, Coqui XTTS-v2, ElevenLabs API
- **LLM Integration:** Ollama (Llama 3), LangChain
- **Audio Processing:** Librosa, PyDub, OpenAI Whisper (forced alignment)
- **UI:** Streamlit (quick) or React (more control)
- **Data Format:** PDF parsing (PyPDF2), text preprocessing (spaCy, NLTK)

## Student Profile

**Preferred Disciplines:**
- AI & Machine Learning (with audio/signal processing)
- Signal Processing / Audio Engineering
- Computer Science with strong Python skills

**Prerequisites:**
- Proficiency in Python
- Understanding of audio processing basics (sampling, frequency, amplitude)
- Interest in NLP and voice synthesis
- Comfortable with training/fine-tuning ML models

**Nice to Have:**
- Experience with Hugging Face transformers
- Knowledge of Hindi language
- Audio engineering background
- Experience with open-source voice models

## Project Timeline

**Total Duration:** 2-3 months

- **Week 1-2:** Research existing voice cloning solutions, set up pipelines (F5-TTS, XTTS-v2, ElevenLabs)
- **Week 3-4:** Text preprocessing, LLM-based emotion tagging
- **Week 5-6:** Fine-tune voice model on author's sample
- **Week 7-8:** Implement forced alignment using Whisper
- **Week 9-10:** Web app integration, testing, documentation
- **Week 11-12:** Comparative analysis report, optimization

## How This Contributes to GAIR Lab

Project Vaani demonstrates:
- **Emotion-aware AI systems:** Moving beyond text-to-speech to emotion-aware synthesis
- **Underrepresented language AI:** Building SOTA tools for Hindi and similar languages
- **Agent-driven content generation:** Using AI agents to annotate and enhance content
- **Open-source benchmarking:** Rigorous evaluation of commercial vs. open-source solutions

## Publications & Impact

Potential outcomes:
- Technical blog post: "Building Emotional Voice Synthesis for Hindi"
- Research paper: "Open-Source vs. Commercial Voice Cloning: A Hindi Language Study"
- Open-source tool used by educators, authors, and accessibility advocates
- Contribution to Hindi NLP community

## Support & Mentorship

- **Lab Director:** Prof. Ashutosh Bhatia
- **AI/ML Mentor:** Skillplot technical team (signal processing, model training)
- **Community:** GAIR Lab WhatsApp project group

## Getting Started

1. **Interested?** [Contact us]({{ '/contact/' | relative_url }}) with your GitHub and brief intro
2. **Setup:** Clone voice model repos and experiment with F5-TTS/XTTS-v2
3. **Onboard:** Join the project WhatsApp group once confirmed

---

**Project Status:** Active  
**Last Updated:** 2024  
**Questions?** [Reach out]({{ '/contact/' | relative_url }})
