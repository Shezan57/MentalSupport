# MentalSupport

AI Mental Health Therapist Made with Medgemma and OpenAI

## Overview

MentalSupport is an advanced AI-powered mental health assistant designed to provide empathetic support, actionable guidance, and critical intervention in times of crisis. Built using Medgemma (via Ollama), OpenAI, Twilio, and modern agent frameworks, it offers both general therapeutic conversation and life-saving emergency escalation features, tailored for accessibility and safety.

---

## Features

### 1. AI-Powered Mental Health Conversations
- **Therapeutic Support:** Uses the Medgemma model with a clinical psychologist persona (“Dr. Emily Hartman”) to deliver emotionally attuned, evidence-based, and strengths-focused guidance.
- **Conversational Flow:** Sustains supportive dialogue, normalizes mental health struggles, and encourages open-ended reflection to uncover root causes.

### 2. Emergency Crisis Response (Twilio Integration)
- **Automatic Emergency Calling:** Detects keywords or situations indicating mental health crises (e.g., suicidal ideation, intent to self-harm).
- **Immediate Action:** Triggers a phone call to a predefined emergency contact or local safety helpline using Twilio’s secure API.
- **Customizable Call Script:** The call can play a customizable pre-recorded message or connect directly to a live responder.

### 3. Local Professional Recommendation
- **Therapist Finder:** When users express the need for professional help or request local specialists, the agent suggests a list of therapists or counseling centers near the user’s provided city or ZIP code.
- **Dynamic Suggestions:** Therapist names and contact information are generated for the specified location, helping bridge users to real, local resources.

### 4. User Interface
- **Streamlit Frontend:** Simple, chat-like interface where users can converse with the AI and receive instant, actionable responses.
- **Session History:** Maintains a running history of the conversation for user reference.

### 5. Robust Backend Architecture
- **FastAPI Backend:** Handles incoming queries, manages the AI agent, and orchestrates tool invocation (therapist, emergency call, etc.).
- **Modular Tools:** All core actions (chat, emergency call, therapist search) are modularized for easy extension and customization.

---

## How It Works

1. **User Initiates Chat:** The user sends a message via the Streamlit frontend.
2. **AI Agent Decides Action:** The backend agent evaluates the message for mental health needs, crisis risk, or professional referral.
3. **Appropriate Tool Invoked:**
   - For support: The Medgemma model generates a tailored therapeutic response.
   - For crisis: The Twilio emergency call function is triggered.
   - For referrals: The agent suggests professionals near the user’s location.

---

## Setup & Installation

### Prerequisites

- Python 3.8+
- Twilio account (for emergency calling)
- Medgemma model via Ollama
- OpenAI API key
- Streamlit, FastAPI, Uvicorn, Langchain, Twilio Python SDK

### Installation Steps

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Shezan57/MentalSupport.git
   cd MentalSupport
   ```

2. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

3. **Configure Environment:**
   - Edit `backend/config.py` and set:
     - `TWILIO_ACCOUNT_SID`
     - `TWILIO_AUTH_TOKEN`
     - `TWILIO_FROM_NUMBER` (your Twilio phone number)
     - `EMERGENCY_CONTACT` (recipient for emergency calls)
     - `OPENAI_API_KEY`
   - Ensure the Medgemma model is available to Ollama.

4. **Run the Backend:**
   ```bash
   cd backend
   uvicorn main:app --reload
   ```

5. **Launch the Frontend:**
   ```bash
   streamlit run ../frontend.py
   ```

---

## Key Files & Structure

- `frontend.py` — Streamlit user interface for chat and responses.
- `backend/main.py` — FastAPI server handling chat and tool invocation.
- `backend/ai_agent.py` — AI agent logic, tool definitions, system prompts.
- `backend/tools.py` — Medgemma querying, Twilio emergency call, therapist search utilities.
- `backend/config.py` — Stores API keys and configuration.
- `README.md` — (This file)

---

## Example Usage

- **General Support:**  
  _User:_ “I feel overwhelmed at work.”  
  _AI:_ “I can sense how difficult this must be. Many people feel this way when work becomes demanding... What sometimes helps is...”

- **Crisis Detection:**  
  _User:_ “I want to hurt myself.”  
  _AI:_ (Triggers Twilio call to emergency contact, responds supportively, and notifies the user that help is being contacted.)

- **Find Therapist:**  
  _User:_ “Can you suggest a therapist in New York?”  
  _AI:_ “Here are some therapists near New York:  
   - Dr. Ayesha Kapoor - +1 (555) 123-4567  
   - Dr. James Patel - +1 (555) 987-6543  
   - MindCare Counseling Center - +1 (555) 222-3333”

---

## Security & Privacy

- **No Conversation Storage:** User conversations are only held in session memory and not permanently logged.
- **Crisis Protocol:** Emergency contact information is stored securely in configuration and used only for crisis intervention.
- **Open Source:** MIT License.

---

## License

See [LICENSE](LICENSE) for details.  
MIT License © 2025 Shezan Ahmed

---

## Disclaimer

_MentalSupport is an aid for emotional support and crisis intervention but is **not a substitute for professional medical advice, diagnosis, or treatment**. In emergencies, always call your local emergency number or seek immediate professional help._
