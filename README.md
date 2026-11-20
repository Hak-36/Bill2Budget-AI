# Kirana Cash-Flow Agent 🏪🤖
**The Zero-Typing Inventory Co-pilot for Bharat's Retail Backbone**

> *“It reads the bills nobody typed and tells you what to buy — inside the cash you actually have.”*

## 📌 Problem Statement (Tech4Bharat 2026 - PS 5.1)
Kiranas lose **15–20% of working capital** to dead stock and **₹5,000–10,000 monthly** to expired goods. Most shops have no billing system, track stock by memory, and order whatever the distributor salesman pushes. They operate entirely on intuition. 

## 💡 The Solution
A voice-first, zero-typing **Agentic AI** mobile app for low-literacy shopkeepers. 
The owner simply:
1. **Takes a photo** of a crinkled distributor bill.
2. **Speaks** their available cash for the day (e.g., *"Aath hazaar"*).
3. The AI **autonomously plans** a reorder list strictly capped at that budget, and drafts a WhatsApp order for one-tap approval.

## 🧠 Defeating the "Week 1" Data Problem
How does the AI know what is a "fast mover" without a POS system? 
*   **Outbound Velocity Engine:** We eliminate "Outbound Blindness" by using passive **UPI credit SMS alerts** and the **timestamp deltas between consecutive distributor bills** to calculate real sell-through velocity and dead stock.
*   **Cold-Start Defense:** The system is pre-seeded with a 120-item regional alias table. It doesn't need to learn from scratch—it proves its worth on Bill #1.
*   **Hyper-Local Guardrail:** The agent cross-checks regional festival calendars (e.g., Sankranti, Diwali, local Jatras) to pre-stock high-velocity items 10 days early, while auto-flagging slow movers 30 days before expiry for bundle discounting.

## ⚙️ Technical Architecture (Why it's a True Agent)
Unlike a simple OCR tool, this system operates on an **Observe-Plan-Act-Verify** loop:
*   **Self-Learning Alias Table:** Uses fuzzy-matching (RapidFuzz) and a JSON cache to map local slang (e.g., *"Lux 3in1"*) to clean SKUs. If confidence is low, it asks the owner for a one-tap voice confirmation and learns instantly.
*   **Knapsack Budget-Solver Tool:** A deterministic mathematical constraint solver that *forces* the AI to never exceed the spoken cash limit. 
*   **Trust UI (Human-in-the-Loop):** Every suggested line item displays its bill source and match confidence. A wrong OCR read costs the owner one tap to reject, not a wrong order. Nothing is sent until the owner taps "Approve."

## 📱 UI Flow (The 4-Screen Journey)
*   **Screen 1 (Scan):** Camera View (Scan Bill).
*   **Screen 2 (Verify):** Voice Budget Input (*"Aaj kitna cash hai?"*) + Alias confirmations.
*   **Screen 3 (Reorder):** Capped Reorder list. Shows a single big metric: **"Estimated dead-stock cash freed this week: ₹X."** Red alert for dead stock.
*   **Screen 4 (Approve):** WhatsApp Draft Approval.

## 💰 Business Model (B2B2C)
*   **Free for the Kirana:** Onboarded by distributor salesmen who want clean, digital orders instead of messy phone calls.
*   **Monetization:** Every approved reorder becomes an anonymized demand signal. We aggregate this data across 1,000 shops and sell hyper-local, real-time demand intelligence to FMCG brands and distributors who currently blind-forecast. *We turn the Kirana from a user into a data node.*

## 🛠️ Tech Stack
*   **Frontend:** React Native / Flutter (Cross-platform mobile)
*   **OCR / Vision:** Google ML Kit / Tesseract
*   **AI Engine:** Gemini 1.5 Flash (for multimodal bill extraction & voice-to-text)
*   **Reasoning:** LangChain / LlamaIndex with RapidFuzz for alias matching.
*   **Backend:** Node.js / Python FastAPI

## 🚀 What's Next (Roadmap)
*   **Phase 1:** Finalize the mobile UI and integrate OCR for 500 common FMCG SKUs.
*   **Phase 2:** Launch pilot with 10 Kiranas in Bengaluru to validate the UPI SMS velocity engine.
*   **Phase 3:** Distribute via FMCG distributor networks and onboard FMCG brands for data analytics.

---
*Built for the Tech4Bharat Hackathon 2026.*
