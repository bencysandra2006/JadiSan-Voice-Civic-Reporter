# JADISAN 🎤🏛️
### *Breaking Literacy Barriers in Civic Governance with AI-Powered Voice Notes*

---

## 🌟 The Vision
**JadiSan** is a voice-first civic reporting platform built to empower the 250M+ non-literate and elderly citizens in India. Instead of navigating complex government apps or websites, users simply send a **WhatsApp Voice Note** in their local dialect. Our AI processes the audio, classifies the grievance, and notifies the relevant authorities instantly.

---

## 🚀 Key Features
- **Voice-to-Action:** No typing required; high-accuracy voice note transcription.
- **AI-Powered Triage:** Integrated with **Google Gemini 1.5 Flash** for automated issue classification, urgency detection, and priority ranking.
- **WhatsApp Bridge:** Seamlessly connected via **Twilio API** to meet users on the platform they already use daily.
- **Real-time Monitoring:** Structured data is instantly logged to **Firebase Firestore** for administrative oversight.

---

## 🏗️ Technical Architecture (Hybrid Edge Strategy)
To ensure high performance while overcoming the memory constraints of free-tier cloud hosting (512MB RAM limit), JadiSan utilizes a **Hybrid Implementation Architecture**:

### **1. Cloud Backend (Render + Node.js)**
* **Role:** Always-on API Gateway.
* **Function:** Receives **Twilio Webhooks**, manages chat flow, and performs Natural Language Processing (NLP) via the **Gemini API**.

### **2. Edge Processing (Local Machine + Ngrok)**
* **Role:** High-Performance Transcription Engine.
* **Reasoning:** Large-scale audio transcription (Whisper) exceeds cloud RAM limits. We utilize **Ngrok** to create a secure tunnel from our local high-memory environment to the internet.
* **Voice Engine:** **OpenAI Whisper** for regional dialect processing.

### **3. The Communication Bridge (Twilio)**
* Acts as the interface between WhatsApp and our server.
* Handles incoming media (Voice Notes) and outgoing AI-generated confirmations.



---

## 🛠️ Tech Stack
| Component | Technology |
| :--- | :--- |
| **Interface** | WhatsApp Business API (via Twilio) |
| **Backend** | Node.js, Express.js |
| **Logic/NLP** | Google Gemini 1.5 Flash |
| **Voice Engine** | OpenAI Whisper (Python/Local) |
| **Database** | Firebase Firestore |
| **Tunneling** | Ngrok (HTTPS Secure Tunnel) |

---

## ⚙️ Installation & Setup

### **Cloud Environment**
1. Clone the repository: `git clone https://github.com/bencysandra2006/JadiSan-Voice-Civic-Reporter.git`
2. Install dependencies: `npm install`
3. Configure your `.env` with `GEMINI_API_KEY`, `TWILIO_SID`, and `TWILIO_TOKEN`.

### **Local Voice Processing**
1. Start your local server: `node index.js`
2. Start the Ngrok tunnel: `ngrok http 3000`
3. Update the **Twilio Sandbox Webhook URL** with your Ngrok forwarding address.
4. Run the transcription engine: `python transcribe.py`

---

## 🔮 Future Roadmap
- **Production Migration:** Deploying the Whisper engine to **Google Cloud Vertex AI** for enterprise-scale processing.
- **Regional Optimization:** Fine-tuning AI for 20+ Indian dialects.
- **Visual Evidence:** Integrating computer vision to verify complaints via uploaded photos (e.g., detecting garbage piles automatically).

---
