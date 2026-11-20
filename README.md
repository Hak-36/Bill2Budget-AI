# Kirana Cash-Flow Agent 🏪🤖
**The Zero-Typing Inventory Co-pilot for Bharat's Retail Backbone**

> *“It reads the bills nobody typed and tells you what to buy — inside the cash and credit you actually have.”*

## 📌 Problem Statement (Tech4Bharat 2026 - PS 5.1)
Kiranas lose **15–20% of working capital** to dead stock and **₹5,000–10,000 monthly** to expired goods. Most shops have no billing system, track stock by memory, and order whatever the distributor salesman pushes (often high-margin dead stock). They operate entirely on intuition and are flying blind on cash flow.

## 💡 The Solution
A voice-first, zero-typing **Agentic AI** mobile app for low-literacy shopkeepers. 
The owner simply:
1. **Takes a photo** of a crinkled distributor bill.
2. **Speaks** their available budget for the day (factoring in both cash-on-hand and upcoming *Udhaar* / credit limits).
3. The AI **autonomously plans** a reorder list strictly capped at that limit, and drafts a WhatsApp order for one-tap approval.

## 🧠 Defeating the "Week 1" Data Problem (Honest Inference)
How does the AI know what is a "fast mover" without a POS system?
*   **Heuristic Velocity Engine:** We acknowledge that aggregate UPI SMS alerts only show total shop revenue, not per-SKU sales. We use the timestamp deltas between consecutive distributor bills paired with UPI cash inflows to generate a *proxy estimate* of SKU velocity.
*   **Human Validation:** The AI proposes the fast-movers based on this proxy, and the owner confirms via a 1-tap voice prompt. The system learns instantly.
*   **Cold-Start Defense:** The system is pre-seeded with a 120-item regional alias table. It doesn't need to learn from scratch—it proves its worth on Bill #1.

## ⚙️ Technical Architecture (Why it's a True Agent)
Unlike a simple OCR tool, this system operates on an **Observe-Plan-Act-Verify** loop:
*   **Multimodal & Phonetic Layer:** Uses Gemini Vision + RapidFuzz + a Self-Learning JSON Alias Table to resolve local shop slang (e.g., *"Lux 3in1"* -> Lux Soap 100g) in milliseconds.
*   **Deterministic Knapsack Budget-Solver:** Unlike hallucinating LLMs, a mathematical constraint solver *guarantees* Total Order Cost ≤ Spoken Budget while maximizing cash turnover. It prevents the AI from ever overspending the shop's money.
*   **Trust UI (Human-in-the-Loop):** Every suggested line item displays its bill source and match confidence. A wrong OCR read costs the owner one tap to reject, not a wrong order delivered.

## 🛡️ Defensibility & Q&A (The Hard Questions)
*   **The Distributor Incentive:** Ground-level salesmen push dead stock for commissions. Our Go-To-Market focuses on **FMCG regional managers**, who mandate our app to gain real-time demand visibility and reduce Kirana credit defaults.
*   **The Udhaar Reality:** The budget cap is not just "cash on hand." The Knapsack solver factors in the shop's available distributor credit limit (7–21 day cycles) so the shop can still reorder even if the cash drawer is empty today.
*   **The Moat vs. Giants (PhonePe/Udaan):** Khatabook tracks credit; Udaan sells inventory. We are a zero-typing procurement agent. Our moat is our vernacular local-name mapping (RapidFuzz) and mathematical budget constraint layer that giants ignore.

## 💰 Business Model (B2B2C)
*   **Free for the Kirana:** Onboarded via FMCG brand managers who want clean, digital orders instead of chaotic phone calls.
*   **Monetization:** Every approved reorder becomes an anonymized demand signal. We aggregate this data across 1,000 shops and sell hyper-local, real-time demand intelligence to FMCG brands and distributors who currently blind-forecast.
*   **Privacy:** All data is strictly aggregated and anonymized before any sale, fully complying with the DPDP Act 2023. We turn the Kirana from a user into a data node, without compromising their privacy.

## 🚀 Roadmap
*   **Phase 1 (Now -> Dec 27 Finale):** Finalize mobile UI and integrate OCR for the top 500 FMCG SKUs. Test on 25+ real regional bills.
*   **Phase 2 (Pilot):** Launch pilot with 15 Kiranas in Bengaluru to validate the heuristic velocity engine and dead-stock reduction.
*   **Phase 3 (Scale):** Distribute via FMCG regional managers and onboard brands for data analytics.

---
*Built for the Tech4Bharat Hackathon 2026.*
