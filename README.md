# Ai-Automation-Journey

Welcome to my AI automation and development journey. I am documenting my progress daily as I build workflows, connect APIs, and learn software fundamentals to solve real-world operational bottlenecks.

---

## Project Log

### Communication Pipeline Foundations
Built an initial workflow automation to handle basic data routing.
* **Tech Stack:** n8n, Webhooks, Gmail API.
* **What I Did:** Configured a workflow engine to listen for an incoming form submission trigger and immediately route that data into a structured email notification.
<img width="1878" height="899" alt="image" src="https://github.com/user-attachments/assets/02c179bf-d9b1-4a98-a62d-cadc3a1c8fae" />




### AI-Powered Motivational Engine & JSON Parsing
Upgraded the architecture by introducing artificial intelligence and data manipulation.
* **Tech Stack:** n8n, OpenAI/LLM Node, JSON, Webhooks.
* **What I Did:** Built a workflow that triggers on a webhook click, calls an AI model to dynamically generate a custom motivational message for someone learning programming, parses the JSON payload, and sends the finalized text straight to my inbox.
* **Concepts Learned:** Deepened my understanding of JSON keys/values and how cross-application API requests communicate across the internet.
<img width="1873" height="960" alt="image" src="https://github.com/user-attachments/assets/9810c310-2831-4df6-8436-474a87a20b46" />




# n8n Essentials: Your First Workflows 🏆

Got the course certificate locked in. Tracking my progress and workflow setups here.

## What I configured to make it work:
* **TriggerManual & SubmitRegistration:** Connected a manual trigger to an HTTP Request node to pass data end-to-end.
* **Header Auth:** Created custom credentials using the exact `X-API-Key` token layout to bypass the academy server security.
* **Query Parameters:** Fixed the data strings (`assessment_id`, `workflow_name`, `tag`) to match the strict grading criteria exactly.

> **Status:** Passed and certified. 🎓
<img width="1121" height="798" alt="image" src="https://github.com/user-attachments/assets/b4ccc1df-187e-414e-8989-fef215f6fa91" />




### Multi-Tenant Database Architecture (Pawn Shop Client Project)

Designed and built a production PostgreSQL schema for a multi-tenant SaaS auction management app — first real paying client project.

- **Tech Stack:** Supabase (PostgreSQL), Lovable, n8n, Railway, Resend
- **What I Did:** Designed a 7-table relational schema (shops, items, item_images, auctions, auction_items, bids, sales_history) with shop-level data isolation baked in from day one, so the same system can serve multiple pawn shops later without restructuring.
- **Concepts Learned:** Multi-tenant SaaS architecture, Postgres enums for data integrity, junction tables for many-to-many relationships, the tradeoffs between array columns vs. separate relational tables for one-to-many data (photos).
- **Debugging:** Cross-checked schema design against a second AI's proposal (Gemini) to validate structural decisions before committing — caught an improvement (separate `item_images` table vs. array column) this way.

*Full project repo: https://github.com/FUNKYFROG25/pawnshop-auction-manager*



### Self-Hosted n8n Migration & Lead Capture Automation

Migrated from n8n Cloud to a self-hosted instance after hitting a trial expiration, then rebuilt and debugged a full lead-scoring automation workflow from scratch on the new infrastructure.

- **Tech Stack:** n8n (self-hosted on Railway), Webhook, Code node (scoring logic), Switch/routing, Slack API, Resend API (email), Google Sheets API, Google Cloud OAuth
- **What I Did:** Built a lead capture workflow that receives form submissions via webhook, scores leads (hot/warm/cold) based on message keywords, and routes them to the correct action — instant Slack alert + auto-reply email for hot leads, lower-priority Slack + sheet logging for warm leads, and silent logging for cold leads.
- **Infrastructure:** Deployed a self-hosted n8n instance on Railway (Postgres + n8n containers) after the cloud trial expired, migrated the exported workflow, and rebuilt all credentials from scratch — Slack Bot Token (OAuth scopes, workspace install) and Google Sheets OAuth2 (Google Cloud Console: OAuth consent screen, test users, redirect URIs).
- **Debugging:** Diagnosed a stubborn Filter node that silently discarded valid data despite a seemingly correct "exists" condition — traced it using n8n's execution logs and worked around it by moving the validation logic into a Code node instead. Also hit an `ENETUNREACH` error on Gmail SMTP, which revealed Railway blocks outbound SMTP ports entirely — switched the email step to the Resend API (HTTPS-based) to resolve it permanently.
- **Concepts Learned:** OAuth2 consent flows and redirect URIs, the difference between SMTP and API-based email delivery (and why cloud hosts often block SMTP), Google Cloud test user restrictions, and the practical limits of visual no-code tools — sometimes a one-line code workaround is more reliable than fighting a UI-based node.

![Self-hosted n8n lead capture workflow]<img width="1562" height="784" alt="image" src="https://github.com/user-attachments/assets/f9b1bf6e-f59f-4bdb-a87c-be31de29e60d" />
