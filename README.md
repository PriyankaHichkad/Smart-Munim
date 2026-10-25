# Smart-Munim (स्मार्ट मुनीम)

> **Hands-free, multilingual voice ledger for Bharat's 12M+ Kirana stores and vendors to manage daily bahi-khata in regional languages.**

---

## The Problem
Small shopkeepers, flour mill operators, and vegetable vendors across India still record **Udhaar (credit)** on physical paper diaries (*Bahi-Khata*). 
- **Hands are rarely clean or free**: While measuring flour, oil, or vegetables, shopkeepers cannot stop to type numbers into accounting apps.
- **Dialect diversity**: Transactions are spoken in colloquial regional languages or mixed dialects (*Hinglish, Tanglish*), e.g., *"रमेश भाई को 5 किलो चीनी दी 220 की, 100 दिया, 120 बाकी"*.
- **Collection friction**: Recovering small credits requires awkward follow-ups.

**Smart-Munim** eliminates typing: shopkeepers simply speak into their phone, and Smart-Munim automatically records the ledger entry, synchronizes with Google Sheets, and speaks back confirmation in their mother tongue.

---

## How It Works (Sarvam AI Pipeline)

```
[Spoken Input in Indic Language]
               │
               ▼
   [Sarvam Saaras v2 (STT)]  --> Accurately transcribes mixed colloquial speech
               │
               ▼
    [Sarvam-2B / Chat LLM]   --> Extracts Customer, Items, Paid, and Due Amount
               │
       ┌───────┴───────────────────┐
       ▼                           ▼
[Sarvam Bulbul v3 (TTS)]   [Digital Bahi-Khata Table]
Spoken Voice Confirmation  Live KPI Metrics + Google Sheets Sync
```

1. **Speech-to-Text (Saaras v2)**: Real-time transcription of Indian languages (Hindi, Tamil, Telugu, Marathi, Bengali, Gujarati, Kannada, etc.).
2. **Financial Entity Extraction (Sarvam-2B)**: Parses customer name, items, total bill, paid amount, and due balance.
3. **Voice Response (Bulbul v3)**: Converts confirmation into natural Indic voice (speakers like *Aditya, Priya, Ritu, Rohan*).
4. **Actionable Ledger & Google Sheets**: Real-time sales KPIs, live Google Sheets synchronization, and 1-click WhatsApp payment reminders.

---

## Quickstart

### 1. Clone the repository
```bash
git clone https://github.com/PriyankaHichkad/Smart-Munim.git
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

## Deploying to Streamlit Cloud

1. Push this folder to your GitHub repo named `Smart-Munim`.
2. Head over to [share.streamlit.io](https://share.streamlit.io/).
3. Select your repository: `PriyankaHichkad/Smart-Munim`, branch: `main`, and set `app.py` as the file path.
4. Click **Advanced settings > Secrets** and paste:
   ```toml
   SARVAM_API_KEY = "your_sarvam_api_key_here"
   ```
5. Click **Deploy**! Your app will be live with a shareable public URL.

---

## Demo Script for Judges

1. **The Hook (30s):** *"India has 12 million Kirana stores. When a shopkeeper has flour or spices on their hands, they can't type into Khatabook. Smart-Munim allows them to manage their entire bahi-khata purely through voice."*
2. **The Demo (60s):**
   - Click the **Hindi Preset** or record live audio: *"रमेश भाई को 5 किलो आटा दिया 180 रुपये का, 100 नकद मिला, 80 उधार"*.
   - Click **Process & Record Entry**.
   - Show how Saaras transcribes it, the AI extracts **₹80 Udhaar**, Bulbul speaks back confirmation in Hindi, and the entry appears in the live ledger.
3. **The Proof & Closer (30s):** Click **Open Shopkeeper's Google Sheet** to show real-time cloud sync, and click **Munimji, Aaj Ka Hisaab Sunao** for a spoken daily financial briefing.
