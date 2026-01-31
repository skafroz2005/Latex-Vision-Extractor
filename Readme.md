# 🦙 LaTeX OCR with Llama 3.2 Vision

A powerful **LaTeX OCR web application** built using **Streamlit** and **Llama 3.2 Vision** that converts images of mathematical equations into **clean, render-ready LaTeX code**.

This project demonstrates the practical use of **Vision-Language Models (VLMs)** for mathematical OCR, combining AI inference with an intuitive web UI.

---

## 🚀 Features

- 📷 Upload images containing mathematical equations
- 🤖 Uses **Llama 3.2 Vision** (via Ollama) for vision-based OCR
- ✨ Outputs **pure LaTeX code** (no explanations, no noise)
- 🧮 Instantly renders LaTeX equations in the browser
- 🧹 Clear/reset functionality
- 🖥️ Clean, responsive Streamlit UI
- 🔒 Runs fully **locally** (no cloud/API dependency)

---

## 🧠 Why This Project?

Traditional OCR tools struggle with mathematical notation. This project solves that problem by leveraging **Vision-Language Models**, making it useful for:

- Students & researchers
- Academic note digitization
- AI-powered document processing
- Math-heavy OCR pipelines

---

## 🏗️ Tech Stack

| Component | Technology |
|--------|-----------|
| Frontend | Streamlit |
| Vision OCR | Llama 3.2 Vision |
| Model Runtime | Ollama |
| Image Handling | Pillow (PIL) |
| Language | Python 3 |

---

## 📂 Project Structure

```bash
Latex-Vision-Extractor/
│
├── app.py               # Main Streamlit application
├── requirements.txt     # Python dependencies
├── README.md            # Project documentation
└── .venv/               # Virtual environment (optional)

⚙️ Installation & Setup
1️⃣ Clone the Repository
git clone https://github.com/your-username/latex-ocr-llama-vision.git
cd latex-ocr-llama-vision

2️⃣ Create & Activate Virtual Environment (Recommended)
python -m venv .venv


Windows

.venv\Scripts\activate


Linux / macOS

source .venv/bin/activate

3️⃣ Install Dependencies
pip install -r requirements.txt


If you don’t have requirements.txt, install manually:

pip install streamlit ollama pillow

4️⃣ Install Ollama

Download and install Ollama from:

https://ollama.com/download


Verify installation:

ollama --version

5️⃣ Pull the Vision Model
ollama pull llama3.2-vision


⚠️ Note: This model requires ~11 GB RAM.
If your system has lower memory, consider using:
ollama pull llava

🟡 STRONGLY RECOMMENDED (Extra Safety)
If You changed the model to llava then Resize image before sending to the model
This reduces memory + speeds up inference.

Replace this:

image = Image.open(uploaded_file)


With this:

image = Image.open(uploaded_file).convert("RGB")
image.thumbnail((1024, 1024))

buf = io.BytesIO()
image.save(buf, format="PNG")
image_bytes = buf.getvalue()

And update Ollama call:

'images': [image_bytes]


▶️ Run the Application
streamlit run app.py