# Company Knowledge Bank: Synapse Academy

## 1. Company Vision & Mission
**Vision:** To democratize advanced technical education by combining personalized AI tutoring with behavioral gamification. 
**Mission:** To make mastering complex topics—from algorithms to cybersecurity and machine learning—as engaging as playing a top-tier video game.

## 2. North Star Metric
**Weekly Active Learners (WAL):** A user is considered a WAL if they have a `sessions_last_7d` count of >= 3 AND an `exercises_completed_7d` count of >= 5. Driving this metric is our ultimate business objective across all segments.

## 3. Target Audience Profiles
* **The Ambitious Upskiller:** Highly motivated (`motivation_score` > 0.7). Driven by skill mastery. Prefers late-evening learning (`preferred_hour` >= 18). Deeply engaged with AI tools.
* **The Casual Competitor:** Moderate motivation (`motivation_score` 0.4 - 0.7). Driven by social status and instant gratification. Highly responsive to push notifications and gamified rewards.

## 4. Product Features Mapping
* **Core Learning:** * *Skill Dashboards:* Tracked via `feature_progress_checked`. Drives feelings of accomplishment.
  * *Curriculum:* Tracked via `exercises_completed_7d`. The core engine of user growth.
* **Gamification:**
  * *Daily Streaks:* Tracked via `streak_current`. Triggers loss-avoidance psychology.
  * *Vault & Rewards:* Tracked via `coins_balance`. Triggers ownership and accumulation drives.
  * *Global Ranks:* Tracked via `feature_leaderboard_viewed`. Triggers social influence and competition.
* **AI Companion:**
  * *AI Debugger/Tutor:* Tracked via `feature_ai_tutor_used`. Triggers empowerment and dynamic problem-solving.

## 5. Pricing Model
* **Freemium Tier:** Access to basic lessons, standard leaderboard, and 100 max `coins_balance` accumulation.
* **Pro Subscription ($15/mo):** Unlimited `feature_ai_tutor_used` queries, premium streak protection, and advanced analytics via `feature_progress_checked`.

## 6. Success Metrics by Persona (Benchmarks)
* **Conversion (Trial to Paid):** Target is 12% conversion. Key leading indicator is interacting with the AI Tutor at least twice during the trial.
* **Retention (Month 1):** Target is 65%. Key leading indicator is maintaining a `streak_current` of > 4 days in the first week.

## 7. Ethical Communication Guidelines
* **Allowed Tones:** Encouraging, witty, value-driven, challenging (in a playful way), analytical, and celebratory.
* **Disallowed Tones:** Guilt-tripping, manipulative, overly aggressive, desperate, or robotic. Never shame a user for a low `notif_open_rate_30d` or a broken streak.

## 8. User Journey Stages & Primary Goals
* **Trial (D0 - D7):** * *Goal:* Conversion. Prove the value of the AI Companion and hook them into their first streak.
* **Paid (D8 - D30):** * *Goal:* Habit Formation. Shift focus from basic metrics to deep `exercises_completed_7d` and community leaderboard ranking.
* **Retention (D31+):** * *Goal:* Advocacy and Upsell (Annual). Focus on overarching `feature_progress_checked` and massive coin accumulations.
* **Churned / Inactive:** * *Goal:* Reactivation. Use high-value hooks (e.g., free AI queries or major feature updates) to drive a single new session.
