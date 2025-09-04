# Mastermind Chatbot (Voice/Text) — Logic Game for Kids

I built this project as a **fun logic game for my kids** so they can **train their minds** and spend **less time on mobile phones**. It blends a classic *Mastermind* puzzle with a simple **intent‑based chatbot** and optional **voice interaction**.

---

## 🎯 What this repo contains
- **Mastermind game** powered by propositional logic constraints (unique 4‑color secret, randomized each round).
- **Automatic feedback**: the program computes how many positions are correct for each guess.
- **Chatbot** that understands simple intents (e.g., greetings, “play game”) using a lightweight neural network.
- **Voice or text mode**: speak to the bot using your mic (optional) or just type.
- **In‑memory only**: by design, the code does **not** save the model/tokenizer/encoder—great for teaching and quick demos.
- **Simple visualization** of the final color sequence.

---

## 🧠 Why I built it
I wanted a screen‑time alternative that still feels engaging. This game encourages **pattern recognition**, **hypothesis testing**, and **logical reasoning**—all while being playful enough to keep kids interested.

---

## 🚀 Quick Start

> **Option 1: Jupyter Notebook (recommended for exploration)**  
> Open the notebook (e.g., `Mastermind_with_Chatbot.ipynb` or the one‑cell version) and **Run All**.

> **Option 2: Python script**  
> If you exported a single `.py` file, just run it with Python.

### 1) Create a virtual environment (optional but recommended)
```bash
python -m venv .venv
# Windows
.venv\Scripts\activate
# macOS/Linux
source .venv/bin/activate
```

### 2) Install dependencies
```bash
pip install "tensorflow==2.15.*" numpy pandas scikit-learn matplotlib pyttsx3 SpeechRecognition
# Voice mode requires a microphone. On Windows, PyAudio can be tricky:
#   pip install pipwin && pipwin install pyaudio
# On macOS: brew install portaudio && pip install pyaudio
```

### 3) Run
- **Notebook**: launch Jupyter, open the notebook, and run all cells.  
- **Script**: run `python mastermind_chatbot.py` (or the filename you saved).  
  - When prompted: choose **voice** (`yes`/`no`).  
  - Ask questions (e.g., *“hello”*, *“play game”*), or type **quit** to exit.  
  - For Mastermind guesses, use the format `color+position` (e.g., `red0`, `blue1`, `green2`, `yellow3`).

---

## 🧩 Mastermind Rules (this variant)
- The system randomly selects **4 distinct colors** from a larger palette.
- The **secret order is hidden**; you’ll see only the set of allowed colors.
- Enter guesses in the form `color+index`, where index is **0–3** (position).
- After each guess, the program tells you how many **positions** are exactly correct.
- The internal knowledge base updates constraints and tries to infer the final solution.

---

## 🗣️ Voice Mode Notes
- Voice mode uses `SpeechRecognition` with the Google recognizer, which needs an **internet connection**.
- If you prefer offline speech recognition, you can swap the recognizer later (e.g., Vosk).  
- TTS uses `pyttsx3`; if it fails on your machine, the game still runs in text mode.

---

## 🧰 Tech Stack
- **Python**, **TensorFlow/Keras**, **scikit‑learn**, **matplotlib**
- **SpeechRecognition**, **pyttsx3**
- A simple **logic** helper (e.g., `And`, `Or`, `Not`, `Symbol`, `Implication`, `model_check`).  
  Ensure `logic.py` (or your logic utilities) is available on `PYTHONPATH`.

---

## 📦 Project Structure (suggested)
```
.
├── notebooks/
│   └── Mastermind_with_Chatbot.ipynb     # Main interactive notebook
├── src/
│   └── logic.py                           # Your logic utilities (And/Or/Not/…)
├── README.md
└── requirements.txt                       # Optional
```

---

## ✅ Tips & Troubleshooting
- **Tiny datasets**: If you use very few samples for the chatbot, stratified splits may fail. Increase test size or disable `stratify` safely.
- **PyAudio on Windows**: use `pipwin install pyaudio`. On macOS, install `portaudio` first.
- **Mic permissions**: allow microphone access when prompted by your OS.

---

## 📝 License
Choose a license that fits your needs (MIT is a common choice for educational projects).

---

## 🙏 Acknowledgments
Thanks to my kids for being the target “users” and for keeping me honest about fun! This project started as a small family experiment to **train the mind** and **spend less time on phones**, and it grew into a teaching tool for logic and AI basics.
