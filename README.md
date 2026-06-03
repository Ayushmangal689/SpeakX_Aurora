# SpeakX Aurora — Intelligent Notification Orchestrator

Aurora is a **data-driven CRM intelligence engine** that segments users, predicts engagement behavior, and generates **personalized notification schedules and messaging strategies** to improve engagement, CTR, and retention.

Originally built for **SpeakX (Kriti 2026)**, Aurora combines **behavioral analytics, machine learning, timing optimization, and LLM-generated messaging** to ensure the **right message reaches the right user at the right time**.

---

# Key Features

- **Behavioral User Segmentation** using clustering on engagement signals
- **LLM-generated notification messaging** personalized for each segment
- **Optimal notification timing prediction** using engagement patterns
- **Dynamic notification frequency control** to prevent fatigue
- **Self-learning feedback loop** improving campaigns over iterations
- **Domain-agnostic architecture** adaptable to any consumer platform

---

# System Architecture

Aurora operates as a **multi-stage intelligent engagement pipeline**.

<img width="6884" height="696" alt="image" src="https://github.com/user-attachments/assets/fd3f9d48-acfc-4707-9f48-47e4fd2d702c" />

Experiment results feed back into the system to continuously **optimize messaging, timing, and engagement strategy**.

---

# Core Components

## 1. Knowledge Bank Engine
Extracts structured product intelligence from a business knowledge base.

Supported formats:

* `.txt`
* `.md`
* `.pdf`

LLM extraction produces: `company_north_star.json` , `feature_goal_map.json`, `allowed_tone_hook_matrix.json`

This design keeps the system **fully domain-agnostic**.

---

## 2. User Data Ingestion
User behavioral data is loaded from: `user_behavioral_data.csv`

Example features:

| Feature                | Description             |
| ---------------------- | ----------------------- |
| days_since_signup      | Time since registration |
| sessions_last_7d       | Recent activity         |
| exercises_completed_7d | Learning engagement     |
| streak_current         | Habit consistency       |
| coins_balance          | Gamification rewards    |
| preferred_hour         | Most active hour        |
| notif_open_rate_30d    | Notification engagement |

The data is validated, cleaned, and normalized to generate behavioral profiles.

---

# Behavioral Segmentation
Users are grouped into 3-6 segments using an **unsupervised ML pipeline**:

<img width="3924" height="448" alt="image" src="https://github.com/user-attachments/assets/6544e4e6-0488-460e-bc7a-cf2e88b602b1" />

Each user also receives interpretable scores according to thier segment:

| Score      | Meaning                      |
| ---------- | ---------------------------- |
| Activeness | Engagement intensity         |
| Propensity | Conversion likelihood        |
| Churn Risk | Probability of disengagement |

Output: `user_segments.csv`

---

# Goal & Journey Builder
Each user segment is mapped to lifecycle goals.

| Lifecycle Stage | Time Window | Objective    |
| --------------- | ----------- | ------------ |
| Trial           | Day 0–7     | Conversion   |
| Paid            | Day 8–30    | Retention    |
| Inactive        | Day 30+     | Reactivation |
| Churned         | Day 60+     | Win-back     |

Output: `segment_goals.csv`

---

# Communication Intelligence

## Theme Engine
Messaging themes are generated using **Octalysis behavioral motivation drives**:

* Epic Meaning
* Accomplishment
* Empowerment
* Ownership
* Social Influence
* Scarcity
* Unpredictability
* Loss Avoidance

Output: `communication_themes.csv`

---

# LLM Message Generation
Notification templates are generated using: **Llama-3.3-70B via Groq API**

For each: `segment × lifecycle stage`


Aurora generates **five structured templates**:
1. Seed
2. Tease
3. Anchor
4. Welcome
5. Wrap-Up

Templates support:
* English + Hindi messaging
* personalization placeholders
* behavioral tone alignment

Output: `message_templates.csv`

---

# Timing Optimization
Aurora predicts optimal notification windows using engagement data.

| Window         | Time        |
| -------------- | ----------- |
| Early Morning  | 06:00–08:59 |
| Mid Morning    | 09:00–11:59 |
| Afternoon      | 12:00–14:59 |
| Late Afternoon | 15:00–17:59 |
| Evening        | 18:00–20:59 |
| Night          | 21:00–23:59 |

Output: `timing_recommendations.csv`

---

# Notification Scheduling
Notification frequency is adjusted based on engagement.

| Activeness Score | Notifications / Day |
| ---------------- | ------------------- |
| High             | 7–9                 |
| Medium           | 5–6                 |
| Low              | 3–4                 |

Schedules are anchored around each user’s **preferred activity hour**.

Output: `user_notification_schedule.csv`

---

# Self-Learning Engine
Campaign results are evaluated using: `experiment_results.csv`

Templates are classified:

| Class   | Criteria  |
| ------- | --------- |
| GOOD    | CTR > 15% |
| NEUTRAL | CTR 5–15% |
| BAD     | CTR < 5%  |

The system then:
* promotes successful templates
* suppresses weak templates
* updates optimal timing windows
* adjusts notification frequency

All changes are logged in: `learning_delta_report.csv`

---

# Tech Stack
### Machine Learning
* Python
* Scikit-learn
* PCA
* UMAP
* Agglomerative Clustering
### Data Processing
* Pandas
* NumPy
### AI / LLM
* Groq API
* Llama-3.3-70B

---

# Project Structure

```
SpeakX_Aurora/
│
├── codebase/
│   ├── SpeakX_Aurora_2617.ipynb
│
├── iteration_0_before_learning/
│   ├── company_north_star.json
│   └── user_notification_schedule.csv
│   └── allowed_tone_hook_matrix.json
│   └── communication_themes.csv
│   └── feature_goal_map.csv
│   └── message_templates.csv
│   └── segment_goals.csv
│   └── timing_recommendations.csv
│   └── user_segments.csv
│
├── iteration_1_after_learning/
│   └── (updated files generated on running the notebook after giving experiment_results.csv)
│   └── user_segments.csv
│   └── message_templates.csv
│   └── timing_Recommendations.csv
│   └── user_notification_schedule.csv
|
├── sample data/
│   └── user_behavioral_data.csv
│   └── knowledge_bank.md
|
├── experiment_results.csv
├── learning_delta_report.csv
└── README.md
```

---

# Installation

Clone the repository:
```
git clone https://github.com/mantis2404/SpeakX_Aurora
```
Create a virtual environment:
```
python3 -m venv venv
```
Activate environment:

Linux / Mac
```
source venv/bin/activate
```
Windows
```
venv\Scripts\activate
```
Install dependencies
```
pip install -r requirements.txt
```
---

# Running the Pipeline

 Configure the Groq API Key
```
api_key = "YOUR_API_KEY"
```

Run notebook:
```
./codebase/SpeakX_Aurora_2617.ipynb
```
The pipeline will generate segmentation, messaging strategies, notification schedules, and improved outputs after learning iterations.

---

# Applications

Project Aurora is **domain-agnostic** and can power engagement systems for:

* EdTech platforms
* SaaS products
* FinTech apps
* Marketplaces
* Subscription services

Replacing the **knowledge base and behavioral dataset** adapts the system to a new domain.
---
Updated project notes
