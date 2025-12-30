# JADISAN 🎤🏛️
### *Empowering the Unheard: A Voice-First WhatsApp Civic Reporting System*

---

## 🌟 Overview
**JadiSan** is a digital bridge for inclusive governance. It allows community members—especially those who are non-literate or elderly—to report civic issues like broken infrastructure or sanitation problems using **WhatsApp Voice Notes**. By leveraging AI to process speech in local dialects, we remove the literacy barrier to civic participation.

---

## 🚀 Key Features
- **Voice-to-Text Reporting:** Users send voice notes; our system handles the rest.
- **AI Triage (Google Gemini):** Automatically categorizes issues (e.g., "Water," "Safety") and detects urgency levels.
- **WhatsApp Integration (Twilio):** Works on the app everyone already uses, requiring no new software downloads.
- **Real-time Database (Firebase):** Stores structured complaints for immediate action by local authorities.

---

## 🏗️ Technical Architecture & Implementation
We utilize a **Hybrid Processing Strategy** to overcome cloud hardware limitations:

1. **Cloud Layer (Node.js/Render):** - Hosts the **Twilio Webhook** to receive incoming WhatsApp data.
   - Interfaces with **Google Gemini 1.5 Flash** for NLP and data structuring.
   
2. **Communication Layer (Twilio):** - Acts as the secure gateway for WhatsApp messages.
   - Manages media URLs for incoming voice notes and sends automated AI-generated responses back to the citizen.

3. **Edge Layer (Local Engine):** - **Note:** Due to the 512MB RAM limit on free cloud tiers, high-fidelity transcription (**OpenAI Whisper**) is run locally to ensure 100% accuracy for regional dialects without server crashes.



### **The Tech Stack**
- **Interface:** Twilio WhatsApp API
- **Intelligence:** Google Gemini AI
- **Transcription:** OpenAI Whisper (Local Edge Engine)
- **Database:** Firebase Firestore
- **Backend:** Node.js, Express

---

## 🛠️ Setup & Installation

### **Prerequisites**
- Node.js & npm
- Python 3.8+ (for local transcription script)
- Twilio Sandbox credentials

### **Configuration**
1. **Clone the repository:**
   ```bash
   git clone [https://github.com/bencysandra2006/JadiSan-Voice-Civic-Reporter.git](https://github.com/bencysandra2006/JadiSan-Voice-Civic-Reporter.git)
Install Backend Dependencies:

Bash

npm install
Environment Variables: Create a .env file and include:

GEMINI_API_KEY

TWILIO_ACCOUNT_SID

TWILIO_AUTH_TOKEN

FIREBASE_CONFIG

Run the Project:

Start Node server: node index.js

Start local voice engine: python transcribe.py

🔮 Future Roadmap
Cloud-Native Speech Scaling: Migrating to Google Cloud Vertex AI for enterprise-scale voice processing.

Regional Dialect Fine-tuning: Enhancing Gemini's accuracy for deep rural dialects and "Hinglish."

Automated Government Integration: Direct API hooks into municipal grievance portals like CPGRAMS.
