# SignSetu — *"Every gesture has a voice"*

**Team Catalyst** | Prototype in active development

SignSetu is a real-time, bi-directional AI communication bridge for the Deaf and Hard of Hearing (DHH) community. It uses computer vision and NLP — no hardware gloves required, just a smartphone or webcam — to translate:

- **Sign → Speech**: camera captures hand gestures, recognizes the sign, speaks it aloud
- **Speech → Sign**: spoken words are converted into a signed sequence shown by a 3D avatar

---

## Problem Statement

There is a massive communication barrier between the Deaf and Hard of Hearing community and the rest of the world. Existing solutions — human interpreters, hardware sensor gloves, dictionary-style translation apps — are too expensive, too static, or too inaccessible for daily continuous use.

- **1.5 billion** people globally experience some degree of hearing loss
- **63 million** people in India have significant auditory impairment, with certified interpreters concentrated in only a handful of large cities
- **73.9%** of the DHH working-age population face employment barriers due to lack of real-time communication support

## Our Approach

| Flow | Pipeline |
|---|---|
| **Sign → Speech** | Camera → Google MediaPipe (hand/pose landmarks) → ML classifier → Text-to-Speech |
| **Speech → Sign** | Microphone → NLP root-word extraction (spaCy/NLTK) → 3D avatar animation (Unity3D) |

Designed to run fully on-device where possible (edge computing / TensorFlow Lite), so it stays fast and usable even with poor or no internet connectivity.

## Tech Stack

- **Computer Vision:** Google MediaPipe
- **ML Models:** PyTorch / TensorFlow, TensorFlow Lite for on-device inference
- **NLP:** spaCy / NLTK for root-word extraction
- **Avatar:** Unity3D (rigged 3D signer)
- **Text-to-Speech:** gTTS / Web Speech API
- **Frontend:** ReactJS / HTML (web), Flutter / React Native (mobile)
- **Backend:** Python (Flask / FastAPI)

## Project Structure

```
signsetu/
├── sign-to-speech/     → Sign-to-Speech prototype (hand tracking + gesture recognition)
├── speech-to-sign/     → Speech-to-Sign prototype (voice input + avatar)
├── docs/               → Pitch deck, architecture notes
└── assets/screenshots/ → App screenshots and demo captures
```

## Current Status

- ✅ Sign-to-Speech: working browser prototype with live MediaPipe hand tracking and gesture recognition (Hello, Help, Thank You, I Love You)
- 🔄 Speech-to-Sign: in progress
- 🔄 Unified dashboard: in progress

## Team

| Name | Role |
|---|---|
| Mahima Jodha | IT (Team Leader) |
| Khusi Agarwal | IT |
| Laxmi Khemada | ECE |
| Akhil Singh | EEE |
| Ajay Singh | IT |

## Limitations & Future Work

- Indian Sign Language (ISL) datasets are far scarcer than ASL — a key gap we plan to close by partnering with Deaf schools, NGOs, and interpreters to build and open-source a labeled ISL dataset
- Continuous, fluid signing is harder to segment than isolated static poses — an area for future model improvement
- Planned: emotional/facial expression support in the avatar, since facial cues carry real grammatical meaning in sign language
