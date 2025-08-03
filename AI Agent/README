## Architecture Overview

### Data Ingestion & Storage  
Raw transactions are received and stored in an analytical SQL database.

### Metadata Catalog / Schema Discovery  
A service exposes tables and columns with human-readable descriptions.

### Aggregation Pipeline / Feature Store  
Nightly (or near-real-time) processing that calculates:  
- Daily TPV  
- Moving averages  
- Segmentations (by entity, product, payment_method)  
- Historical metrics (previous day, week, month)  
- Maintains time series data  

### Anomaly & Growth Detection Engine  
Statistical algorithms and trained models to detect:  
- Day-over-day / week-over-week / month-over-month growth  
- Anomalies by segment using z-score, EWMA, Isolation Forest, seasonal residuals  

### AI Assistant / Generator  
LLM (via LangChain) with access to schema catalog and SQL connectors.  
The assistant translates intents like _“show today’s TPV compared to last week”_ into queries, interprets results, and generates natural language summaries and recommendations.

### Orchestration & Execution  
AWS Step Functions; n8n  

### Distribution / Notifications  
Daily delivery via channels: Slack, email, WhatsApp  

### Validation & Observability  
Ensures quality of outputs through KPI regression tests, sanity checks, structured logging (CloudWatch), auditing, and failure alerts.

### Security & Governance  
Granular IAM, encryption at rest and in transit, VPC, KMS, auditing via CloudTrail, access control for LLM and sensitive data.

---

## Advanced Extensions

### ChatOps Interface  
Users can ask questions like _“What was the Pix TPV yesterday compared to this month’s average?”_ directly via Slack.  
The bot uses LangChain to generate and run the query, responding inline.

### Personalization  
Each stakeholder (Ops, Growth, Finance) receives a tailored view with language and thresholds adapted to their profile.

---

## Proof of Concept — Integration with n8n

As a proof of concept, I developed a simple model using **n8n**, with the goal of exploring the possibility of automated interaction with data.

Due to time constraints, the model queries a pre-processed table in Google Sheets. It can read the data and perform simple aggregations based on received questions.

The flow includes chat memory, allowing a small context window for more natural user interactions.

Along with this report, I’m providing:
- A demo video of the model in action  
- The `.json` file of the n8n workflow, which can be imported for replication  

---

## Next Steps and Limitations

With more time, it would be possible to structure a more robust model directly in **n8n**, where:
- The model would interact with a real database  
- Execute dynamic SQL queries instead of just spreadsheet lookups  

However, for scalable and critical solutions, I do **not recommend** using no-code tools like n8n for this type of analytical logic.  
They are great for prototyping, but have limitations in terms of security, flow control, and performance — especially in scenarios involving multiple users or large volumes of data.

Video -> https://www.youtube.com/watch?v=o7oBi4AxJdo
