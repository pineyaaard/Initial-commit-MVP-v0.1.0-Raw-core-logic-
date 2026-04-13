# 🚀 TTTAP Core Engine (CAR DAMAGES AI ESTIMATOR) - Demo Release v3.0

**🎬 Watch Demo Video:** 



https://github.com/user-attachments/assets/ebbc4f2f-acb5-43fc-bf99-8cdb5cbd50c9



# TTTAP Core v3.0 (Alpha MVP)
**Hybrid AI Engine for Automated Auto Body Repair Estimation**

**⚙️ Models:** Gemini 3.0 Flash (Vision + Caching) / Gemini 3.1 Pro (Search & Video)
**📍 Focus:** Czech Automotive Market (Prague/EU)
**💰 Target Efficiency:** ~2 Kč per standard request

---

## 🚀 Overview
TTTAP Core is a professional-grade hybrid engine that transforms visual data (photos/videos) into a detailed repair estimate based on real-world Czech flat-rate labor hours (**Normohodiny / Nh**). Version 0.3.0 marks the transition from a simple calculator to a robust SaaS platform designed for garage deployment.

---

## 🔥 Key Features in v3.0

### 1. Advanced AI Logic (Prompt v3.0)
The estimation engine now uses a monolithic "Audit Layer" to apply complex heuristics:
* **Anti-Hallucination for Compact Cars:** Specifically tuned for vehicles like Toyota iQ or Smart to prevent unnecessary parts replacement.
* **Hybrid Text+Photo Input:** The AI now incorporates user notes (e.g., "add fender repair") even if damage isn't clearly visible in photos.
* **Floor Heuristics:** Implements a strict price floor for severe side impacts (~60-65k Kč) to ensure market-realistic estimates.
* **Repair-First Policy:** Prioritizes metalwork and soldering (PDR/Bumper soldering) over costly replacements unless panels are structurally compromised.

### 2. Multimedia & Video Engine
* **Video Fly-around Support:** Integrated Google GenAI `File API` to process 360-degree vehicle videos.
* **Intelligent Model Routing:** * **Flash + Context Caching:** Used for standard photo audits to minimize costs (up to 60% savings on input tokens).
    * **Pro Model:** Automatically triggered for video analysis or high-volume (6+ files) uploads.

### 3. Localization & Identification
* **RapidAPI VIN Integration:** Upgraded from NHTSA to a commercial-grade decoder for better hit rates on European-spec vehicles (Skoda, VW, etc.).
* **i18n Support:** Dynamic switching between **Czech, Russian, and English**.

### 4. Dual-Role Interface
* **Client View:** Clean, retail-focused summary with final costs.
* **Master View (Garage Mode):** Unlocks wholesale pricing (velkoobchod), profit margin analysis, and direct supplier links (local).

---

## 🧠 Optimization Strategy (Cost Control)

| Action | Model | Frequency | Estimated Cost |
| :--- | :--- | :--- | :--- |
| **Standard Photo Audit** | Flash + Cache | Every request | **1–2 Kč** |
| **Video Audit** | Pro Model | Rare / Specialized | **8–10 Kč** |
| **Deep Parts Search** | Pro + Google Search | On-demand (Button click) | **5–8 Kč** |

> **Context Caching:** By caching the 4,000+ token "System Instruction" on the server, we prevent high recurring costs for the monolithic prompt.

---

## 🛠 Tech Stack
* **Frontend:** React, Tailwind CSS, Vite.
* **Backend:** Node.js (Express), Vite Middleware.
* **AI Engine:** `@google/genai` (Context Caching enabled).
* **Database:** Firebase Firestore (Lead Management).
* **VIN Service:** Internal SpareParts Shop VIN Decoder, Internal database and Vortex (for American Cars)
* **Parts Search:** Google Search Tool integration via Gemini Pro.

---

## ⚠️ Known Limitations (Alpha)
* **Video Frame Breakdown:** Currently working on manual frame extraction to further reduce Pro model costs.
* **Dynamic Links:** AI Search Agent may occasionally generate broken URLs if OEM numbers are missing from common databases.
* **Heuristic Fallbacks:** When real-time price scraping fails, the system defaults to "Catalog Heuristics" based on vehicle class.

---

**🏷 Version:** Demo Release v3.0 (MVP)
**🏗 Developer Status:** Deploying to pilot partner garages next week.
