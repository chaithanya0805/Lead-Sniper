# 🎯 GitHub Lead Sniper (AI-Powered Workflow Automation)

An automated lead qualification and outreach pipeline built on **n8n** that detects repository stars, filters high-value developer leads, generates personalized sales pitches using **Google Gemini LLM**, and alerts the team via **Discord Webhooks**.

---

## ⚡ Architecture & Pipeline

```text
GitHub Star Event (Webhook)
         │
         ▼
Fetch GitHub User Profile (HTTP Request)
         │
         ▼
Lead Qualification Filter (If Node: Followers > 100 OR Repos > 50)
         │
   ┌─────┴─────┐
   │           │
[True]      [False] ──> Drop Execution (Filtered out low-intent leads)
   │
   ▼
Generate Personalized AI Pitch (Basic LLM Chain + Google Gemini)
         │
         ▼
Send Formatted Alert (Discord Webhook / HTTP Request)
