# 📒 Smart-Munim (स्मार्ट मुनीम)

> **🎙️ Hands-free, multilingual voice ledger for Bharat's 12M+ Kirana stores and vendors to manage daily bahi-khata in regional languages.**

[![Streamlit](https://static.streamlit.io/badges/streamlit_badge_black_white.svg)](https://streamlit.io)
[![Sarvam AI](https://img.shields.io/badge/Powered%20By-Sarvam%20AI-orange.svg)](https://sarvam.ai)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

---

## 🇮🇳 The Problem
Small shopkeepers, flour mill operators, and vegetable vendors across India still record **Udhaar (credit)** on physical paper diaries (*Bahi-Khata*). 
- **Hands are rarely clean or free**: While measuring flour, oil, or vegetables, shopkeepers cannot stop to type numbers into accounting apps.
- **Dialect diversity**: Transactions are spoken in colloquial regional languages or mixed dialects (*Hinglish, Tanglish*), e.g., *"रमेश भाई को 5 किलो चीनी दी 220 की, 100 दिया, 120 बाकी"*.
- **Collection friction**: Recovering small credits requires awkward follow-ups.

**Smart-Munim** eliminates all typing: shopkeepers simply speak into their phone, and Smart-Munim automatically records the ledger entry and speaks back confirmation in their mother tongue.

---

## ⚡ How It Works (Sarvam AI Pipeline)

```
[🎙️ Spoken Input in Indic Language]
               │
               ▼
   [Sarvam Saaras v2 (STT)]  --> Accurately transcribes mixed colloquial speech
               │
               ▼
    [Sarvam-2B / Chat LLM]   --> Extracts Customer, Items, Paid, and Due Amount
               │
       ┌───────┴───────────────────┐
       ▼                           ▼
[Sarvam Bulbul v1 (TTS)]   [Digital Bahi-Khata Table]
Spoken Voice Confirmation  Live KPI Metrics + WhatsApp Reminder
```

1. **Speech-to-Text (Saaras v2)**: Real-time transcription of Indian languages (Hindi, Tamil, Telugu, Marathi, Bengali, Gujarati, Kannada, etc.).
2. **Financial Entity Extraction (Sarvam-2B)**: Parses customer name, items, total bill, paid amount, and due balance.
3. **Voice Response (Bulbul v1)**: Converts confirmation into natural Indic voice (speakers like *Meera, Pavithra, Arvind*).
4. **Actionable Ledger**: Real-time sales KPIs + 1-click WhatsApp payment reminders.

---

## 🚀 Quickstart (Local Run in 2 Minutes)

### 1. Clone the repository
```bash
git clone https://github.com/your-username/Smart-Munim.git
cd Smart-Munim
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Add your Sarvam API Key
Create a `.env` file or copy from `.env.example`:
```bash
cp .env.example .env
```
Inside `.env`, set:
```ini
SARVAM_API_KEY=your_sarvam_api_key_here
```

### 4. Run the Streamlit App
```bash
streamlit run app.py
```

---

## ☁️ Deploying to Streamlit Cloud (Hackathon Ready)

1. Push this folder to your GitHub repo named `Smart-Munim`.
2. Head over to [share.streamlit.io](https://share.streamlit.io/).
3. Select your repository, branch (`main`), and set `app.py` as the file path.
4. Click **Advanced settings > Secrets** and paste:
   ```toml
   SARVAM_API_KEY = "your_sarvam_api_key_here"
   ```
5. Click **Deploy**! Your app will be live with a shareable public URL in under 2 minutes.

---

## 🎯 45-Minute Hackathon Demo Script (For Judges)

1. **The Hook (30s):** *"India has 12 million Kirana stores. When a shopkeeper has flour or spices on their hands, they can't type into Khatabook. What if they could just speak to an AI Munimji?"*
2. **The Demo (60s):**
   - Click the **🌾 Hindi Preset** or record live audio: *"रमेश भाई को 5 किलो आटा दिया 180 रुपये का, 100 नकद मिला, 80 उधार"*.
   - Click **Process & Record Entry**.
   - Show how Saaras transcribes it, the AI extracts **₹80 Udhaar**, Bulbul speaks back confirmation in Hindi, and the entry appears in the live ledger.
3. **The Closing (30s):** Click the **"📲 Send via WhatsApp"** button to show instant payment recovery link.

---

## 📜 License
MIT License. Built for the Hackathon.
