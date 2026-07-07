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
