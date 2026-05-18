# **Data Lifecycle Self-paced Checklist**

**Audience:** AI Fellow with Python and SQL knowledge  
**Goal:** Build the ability to design, implement, evaluate, and improve the full data lifecycle for AI systems.

Use this checklist at your own pace. For each area:

* **Core checklist** \= everyone should complete this.  
* **Stretch checklist** \= deeper work for stronger students.  
* **Additional Task for specialization** \= ways to specialize based on interest.

---

# **1\. Understand the Full Data Lifecycle**

## **Core Checklist**

- [x] ~~I can define the major stages of the data lifecycle:~~  
      - [x] ~~Data generation~~  
      - [x] ~~Data collection~~  
      - [x] ~~Ingestion~~  
      - [x] ~~Storage~~  
      - [x] ~~Cleaning~~  
      - [x] ~~Transformation~~  
      - [x] ~~Labeling~~  
      - [x] ~~Validation~~  
      - [x] ~~Dataset versioning~~  
      - [x] ~~Model training use~~  
      - [x] ~~Monitoring~~  
      - [x] ~~Governance~~  
      - [x] ~~Archival~~  
      - [x] ~~Deletion~~  
- [x] I can explain how poor data handling can cause:  
      - [x] Model bias  
      - [x] Data leakage  
      - [x] Poor generalization  
      - [x] Unstable model performance  
      - [x] Privacy risk  
      - [x] Compliance risk  
- [x] I can draw a full lifecycle map for one AI product.

## **Stretch Checklist**

- [x] I can identify feedback loops between users, data, models, predictions, and future data.  
- [x] ~~I can explain how data quality affects model reliability in production.~~  
- [x] I can compare a research dataset workflow with a production data workflow.

## **Think/Plan Data lifecycle for any of the following**

* NLP system  
* Computer vision system  
* Recommendation system  
* Forecasting system  
* RAG chatbot  
* Learning analytics system  
* Fraud detection system  
* Agentic AI system

---

# **2\. Identify Data Sources and Data Generation Processes**

## **Core Checklist**

- [x] I can identify different data sources:  
      - [x] Application logs  
      - [x] User events  
      - [x] Databases  
      - [x] APIs  
      - [x] Documents  
      - [ ] Images  
      - [ ] Audio  
      - [ ] Video  
      - [ ] Sensor data  
      - [x] Human annotations  
      - [x] Synthetic data  
- [x] I can describe how a dataset was generated.  
- [x] I can identify the schema, frequency, format, and business meaning of a data source.  
- [x] I can distinguish between:  
      - [x] Operational data  
      - [x] Analytical data  
      - [x] Training data  
      - [x] Evaluation data  
      - [x] Feedback data

## **Stretch Checklist**

- [x] I can identify source-level problems:  
      - [x] Missing events  
      - [x] Duplicated records  
      - [x] Selection bias  
      - [x] Survivorship bias  
      - [x] Measurement error  
      - [x] Proxy variables  
      - [x] Instrumentation gaps  
- [x] I can judge whether a source is suitable for a given AI use case.

## **Path for Specialization**

* Study user behavior data.  
* Study transactional data.  
* Study text/document data.  
* Study image or video data.  
* Study sensor or time-series data.  
* Study human feedback data.

---

# **3\. Design Data Collection and Instrumentation**

## **Core Checklist**

- [x] I can define:  
      - [x] Instrumentation  
      - [x] Event tracking  
      - [x] Logging  
      - [x] Telemetry  
      - [x] Metadata  
      - [x] Consent  
- [x] I can design an event schema for a product or AI workflow.  
- [x] My event schema includes:  
      - [x] Event name  
      - [x] Event description  
      - [x] Timestamp  
      - [x] User ID or session ID  
      - [x] Event properties  
      - [x] Source system  
      - [x] Consent status  
      - [x] Data sensitivity level  
- [x] I can explain why data collection should be designed before model development.

## **Stretch Checklist**

- [x] I can detect poorly defined events.  
- [x] I can improve an existing tracking plan.  
- [x] I can design instrumentation for model monitoring and user feedback.  
- [x] I can design event collection for online learning or agentic AI systems.

## **Paths for Data Collection Implementation**

* Product analytics tracking  
* Learning platform tracking  
* Chatbot interaction logging  
* Coding assistant telemetry  
* Recommendation feedback tracking  
* Human-in-the-loop feedback tracking

---

# **4\. Ingest Data Reliably**

## **Core Checklist**

- [x] I can define:  
      - [x] Batch ingestion  
      - [x] Streaming ingestion  
      - [x] API ingestion  
      - [x] CDC  
      - [x] Webhook  
      - [x] Message queue  
- [x] I can ingest data from:  
      - [x] CSV files  
      - [x] JSON files  
      - [x] APIs  
      - [x] SQL databases  
- [x] I can write Python code to extract, validate, and save data.  
- [x] I can write SQL queries to load and inspect ingested data.  
- [x] I can detect common ingestion issues:  
      - [x] Duplicate records  
      - [x] Missing fields  
      - [x] Schema changes  
      - [x] Late-arriving data  
      - [x] Partial loads

## **Stretch Checklist**

- [x] I can explain the trade-offs between batch and streaming ingestion.  
- [x] I can design idempotent ingestion pipelines.  
- [x] I can reason about at-least-once and exactly-once processing.  
- [x] I can design an ingestion system for near-real-time AI use cases.

## **Path for Ingestion Pipeline**

* Batch analytics pipeline  
* Streaming recommendation pipeline  
* API-based data collector  
* Event-driven AI pipeline  
* LLM conversation log ingestion  
* Computer vision data ingestion

---

# **5\. Design Data Storage and Architecture**

## **Core Checklist**

- [x] I can define:  
      - [x] Database  
      - [x] Data warehouse  
      - [x] Data lake  
      - [x] Lakehouse  
      - [x] Object storage  
      - [x] Feature store  
      - [x] Vector database  
      - [x] Metadata store  
- [x] I can explain the difference between:  
      - [x] OLTP systems  
      - [x] OLAP systems  
      - [x] ML-oriented storage  
- [x] I can organize data into layers:  
      - [x] Raw layer  
      - [x] Cleaned layer  
      - [x] Curated layer  
      - [x] Feature layer  
      - [x] Training dataset layer  
      - [x] Evaluation dataset layer  
      - [x] Serving layer  
- [x] I can choose appropriate formats:  
      - [x] CSV  
      - [x] JSON  
      - [x] JSONL  
      - [x] Parquet  
      - [x] SQL tables  
      - [x] Embedding indexes

## **Stretch Checklist**

- [x] I can design storage with partitioning and indexing.  
- [x] I can compare storage options based on cost, latency, access patterns, and governance.  
- [x] I can design a lakehouse-style architecture with versioning and lineage.  
- [ ] I can design storage for multimodal AI data.

## **Paths to explore**

* Warehouse architecture  
* Lakehouse architecture  
* Feature store design  
* Vector database design  
* Multimodal dataset storage  
* Metadata and lineage systems

---

# **6\. Model Data with Clear Schemas**

## **Core Checklist**

- [x] I can define:  
      - [x] Schema  
      - [x] Primary key  
      - [x] Foreign key  
      - [x] Normalization  
      - [x] Denormalization  
      - [x] Fact table  
      - [x] Dimension table  
      - [x] Star schema  
      - [x] Semantic layer  
- [x] I can design relational tables with clear:  
      - [x] Entities  
      - [x] Keys  
      - [x] Relationships  
      - [x] Timestamps  
      - [x] Granularity  
      - [x] Constraints  
- [x] I can write SQL transformations to create analytical tables.  
- [x] I can identify schema problems:  
      - [x] Missing keys  
      - [x] Ambiguous entities  
      - [x] Inconsistent granularity  
      - [x] Many-to-many errors  
      - [x] Duplicated entities

## **Stretch Checklist**

- [x] I can model slowly changing dimensions.  
- [x] I can design temporal joins for ML.  
- [x] I can reason about entity resolution.  
- [x] I can design schemas for predictions, labels, feedback, and outcomes.

## **Different Examples to think about**

* E-commerce schema  
* Education platform schema  
* Healthcare data schema  
* Financial transaction schema  
* Recommender system schema  
* LLM interaction schema

---

# **7\. Clean and Preprocess Data**

## **Core Checklist**

- [x] I can identify and handle:  
      - [x] Missing values  
      - [x] Duplicate records  
      - [x] Outliers  
      - [x] Invalid categories  
      - [x] Encoding issues  
      - [x] Parsing errors  
      - [x] Noisy labels  
- [x] I can clean data using:  
      - [x] Python  
      - [x] SQL  
- [x] I can standardize:  
      - [x] Dates  
      - [x] Text fields  
      - [x] Categorical values  
      - [x] Numeric values  
      - [x] Identifiers  
- [x] I can explain the difference between cleaning for analytics and preprocessing for ML.

## **Stretch Checklist**

- [x] I can analyze whether missing data is random, systematic, or informative.  
- [x] I can detect when preprocessing introduces bias.  
- [x] I can detect when preprocessing introduces leakage.  
- [x] I can build reusable preprocessing pipelines.  
- [x] I can handle schema drift and train-serving skew.

## **Explore Tools and techniques for**

* Tabular preprocessing  
* Text preprocessing  
* Image preprocessing  
* Time-series preprocessing  
* Log preprocessing  
* Multimodal preprocessing

---

# **8\. Transform Data and Engineer Features**

## **Core Checklist**

- [x] I can define:  
      - [x] Feature  
      - [x] Target  
      - [x] Label  
      - [x] Aggregation  
      - [x] Windowing  
      - [x] Encoding  
      - [x] Embedding  
      - [x] Normalization  
- [x] I can create:  
      - [x] Numerical features  
      - [x] Categorical features  
      - [x] Temporal features  
      - [x] Text features  
      - [x] Aggregated features  
- [x] I can build feature tables using SQL.  
- [x] I can explain why feature engineering depends on prediction time.

## **Stretch Checklist**

- [x] I can detect:  
      - [x] Feature leakage  
      - [x] Target leakage  
      - [x] Proxy leakage  
      - [x] Post-outcome variables  
- [x] I can design point-in-time correct features.  
- [x] I can compare manually engineered features with learned representations.  
- [x] I can design reusable feature pipelines for both training and inference.

## **Paths for feature engineering**

* Churn prediction features  
* Fraud detection features  
* Ranking features  
* Forecasting features  
* Recommender system features  
* Embedding-based features  
* Agent evaluation features

---

# **9\. Create and Evaluate Labels**

## **Core Checklist**

- [x] I can define:  
      - [x] Label  
      - [x] Annotation  
      - [x] Gold standard  
      - [x] Weak label  
      - [x] Synthetic label  
      - [x] Human feedback  
      - [x] Inter-annotator agreement  
      - [x] Labeling guideline  
- [x] I can write labeling instructions for a classification or evaluation task.  
- [x] I can inspect labels for:  
      - [x] Ambiguity  
      - [x] Inconsistency  
      - [x] Class imbalance  
      - [x] Annotator bias  
      - [x] Missing examples  
- [x] I can calculate simple label agreement metrics.

## **Stretch Checklist**

- [x] I can compare:  
      - [x] Human labeling  
      - [x] Weak supervision  
      - [x] Synthetic labeling  
      - [x] Active learning  
      - [x] Programmatic labeling  
- [x] I can design a labeling workflow with:  
      - [x] Guidelines  
      - [x] Examples  
      - [x] Quality checks  
      - [x] Review  
      - [x] Adjudication  
      - [x] Feedback loops

## **Different Types of labelling implementation**

- [ ] Image labeling  
- [x] Text labeling  
- [x] Code evaluation labeling  
- [x] Conversation quality labeling  
- [x] Search result ranking  
- [x] Safety evaluation labeling  
- [x] RLHF-style feedback

---

# **10\. Validate and Test Data Quality**

## **Core Checklist**

- [x] I can define data quality dimensions:  
      - [x] Accuracy  
      - [x] Completeness  
      - [x] Consistency  
      - [x] Validity  
      - [x] Uniqueness  
      - [x] Timeliness  
      - [x] Freshness  
      - [x] Integrity  
- [x] I can write validation checks for:  
      - [x] Schema  
      - [x] Null values  
      - [x] Ranges  
      - [x] Categories  
      - [x] Duplicates  
      - [x] Uniqueness  
      - [x] Referential integrity  
      - [x] Freshness  
- [x] I can explain how data quality issues become model quality issues.

## **Stretch Checklist**

- [x] I can distinguish between a pipeline bug and a real-world data shift.  
- [x] I can prioritize tests based on business and model risk.  
- [x] I can design statistical validation checks.  
- [x] I can design automated alerts for data quality failures.

## **Setup Validation Implementation for**

- [x] Validation for tabular ML  
- [x] Validation for event logs  
- [x] Validation for labels  
- [ ] Validation for embeddings  
- [x] Validation for model inputs  
- [x] Validation for model outputs  
- [x] Validation for evaluation datasets

---

# **11\. Version Data and Track Lineage**

## **Core Checklist**

- [x] I can define:  
      - [x] Dataset versioning  
      - [x] Lineage  
      - [x] Provenance  
      - [x] Metadata  
      - [x] Snapshot  
      - [x] Experiment tracking  
      - [x] Reproducibility  
- [x] I can save dataset versions.  
- [x] I can document how each dataset was created.  
- [x] I can record:  
      - [x] Dataset source  
      - [x] Schema version  
      - [x] Transformation code  
      - [x] Processing date  
      - [x] Dataset hash or ID  
      - [x] Training parameters  
      - [x] Model outputs

## **Stretch Checklist**

- [x] I can trace a model result back to the source data.  
- [x] I can compare dataset versioning approaches for research and production.  
- [x] I can design lineage-aware ML pipelines.  
- [x] I can connect dataset versions to model versions and evaluation results.

## **Advance Versioning practice**

- [x] Git-based dataset tracking  
- [ ] DVC-style workflows  
- [ ] MLflow-style experiment tracking  
- [x] Warehouse-native versioning  
- [x] Metadata catalog design  
- [x] Audit trail design

---

# **12\. Design Train, Validation, Test, and Evaluation Sets**

## **Core Checklist**

- [x] I can define:  
      - [x] Training set  
      - [x] Validation set  
      - [x] Test set  
      - [x] Holdout set  
      - [x] Benchmark  
      - [x] Cross-validation  
      - [x] Stratification  
      - [x] Temporal split  
- [x] I can create train/validation/test splits using Python.  
- [x] I can create train/validation/test splits using SQL.  
- [x] I can explain why random splitting is not always appropriate.

## **Stretch Checklist**

- [x] I can detect leakage from:  
      - [x] Entity overlap  
      - [x] Time leakage  
      - [x] Duplicate records  
      - [x] Repeated users  
      - [x] Shared sessions  
      - [x] Future information  
- [x] I can design:  
      - [x] Time-aware splits  
      - [x] Group-aware splits  
      - [x] Distribution-aware splits  
      - [x] Stress-test datasets  
      - [x] Adversarial evaluation datasets

## **Evaluation to Try**

- [x] Classification evaluation  
- [x] Regression evaluation  
- [x] Forecasting evaluation  
- [x] Ranking evaluation  
- [ ] Recommender evaluation  
- [x] RAG evaluation  
- [x] LLM response evaluation  
- [x] Safety evaluation

---

# **13\. Govern Data Responsibly**

## **Core Checklist**

- [x] I can define:  
      - [x] PII  
      - [x] Sensitive data  
      - [x] Consent  
      - [x] Access control  
      - [x] Data retention  
      - [x] Anonymization  
      - [x] Pseudonymization  
      - [x] Data minimization  
      - [x] Purpose limitation  
- [x] I can classify fields by sensitivity.  
- [x] I can define basic handling rules for sensitive data.  
- [x] I can explain why AI systems create special governance risks.

## **Stretch Checklist**

- [x] I can identify risks related to:  
      - [x] Privacy  
      - [x] Fairness  
      - [x] Consent  
      - [x] Surveillance  
      - [x] Misuse  
      - [x] Memorization  
      - [x] Re-identification  
- [x] I can design a governance plan covering:  
      - [x] Access  
      - [x] Consent  
      - [x] Retention  
      - [x] Deletion  
      - [x] Monitoring  
      - [x] Auditability

## **Path to explore**

* Education data governance  
* Healthcare data governance  
* Financial data governance  
* Workplace analytics governance  
* LLM product governance  
* Public-sector AI governance

---

# **14\. Secure Data Across the Lifecycle**

## **Core Checklist**

- [x] I can define:  
      - [x] Authentication  
      - [x] Authorization  
      - [x] Encryption  
      - [x] Secrets management  
      - [x] Least privilege  
      - [x] Audit log  
      - [x] Data exfiltration  
- [x] I can design basic access control for:  
      - [x] Raw data  
      - [x] Cleaned data  
      - [x] Training data  
      - [x] Evaluation data  
      - [x] Production data  
- [x] I can identify common security risks in data pipelines.

## **Stretch Checklist**

- [x] I can design least-privilege access policies.  
- [x] I can reason about credential rotation and secret handling.  
- [x] I can design secure data sharing workflows.  
- [x] I can identify model-related data leakage risks.  
- [x] I can create a basic data incident response plan.

## **Choose Your Path**

* Cloud data security  
* Enterprise data access  
* Research data security  
* AI product telemetry security  
* Secure internal tooling  
* Sensitive dataset sandboxing

---

# **15\. Automate Data Pipelines**

## **Core Checklist**

- [x] I can define:  
      - [x] DAG  
      - [x] Task  
      - [x] Dependency  
      - [x] Scheduler  
      - [x] Retry  
      - [x] Backfill  
      - [x] Checkpoint  
      - [x] Idempotency  
- [x] I can convert a notebook workflow into a pipeline.  
- [x] I can structure a pipeline into:  
      - [x] Extraction  
      - [x] Transformation  
      - [x] Validation  
      - [x] Loading  
      - [x] Reporting or output generation  
- [x] I can inspect logs to diagnose simple pipeline failures.

## **Stretch Checklist**

- [x] I can design workflows with retries.  
- [x] I can design workflows with backfills.  
- [x] I can design workflows with dependency management.  
- [x] I can design workflows with validation gates.  
- [x] I can design workflows with alerting.  
- [x] I can explain why notebooks are insufficient for production workflows.

## **Automate Data pipeline implementation path**

* Analytics pipeline  
* ML training pipeline  
* LLM evaluation pipeline  
* Data labeling pipeline  
* Streaming workflow  
* RAG refresh pipeline

---

# **16\. Prepare Data for Model Training and Fine-Tuning**

## **Core Checklist**

- [x] I can define:  
      - [x] Training data  
      - [x] Validation data  
      - [x] Test data  
      - [x] Prompt-response pair  
      - [x] Instruction tuning data  
      - [x] Preference data  
      - [x] Negative sample  
      - [x] Hard example  
- [x] I can format data for:  
      - [x] Classical ML  
      - [ ] Deep learning  
      - [ ] LLM fine-tuning  
      - [x] Evaluation workflows  
- [x] I can prepare a clean supervised learning dataset.  
- [x] I can document dataset assumptions and limitations.

## **Stretch Checklist**

- [x] I can detect:  
      - [x] Overrepresentation  
      - [x] Underrepresentation  
      - [x] Data contamination  
      - [x] Low-quality examples  
      - [x] Label noise  
      - [x] Leakage  
- [x] I can decide whether performance is more likely to improve from:  
      - [x] More data  
      - [x] Better data  
      - [x] Cleaner labels  
      - [x] Better sampling  
      - [x] Better model architecture  
- [x] I can design data mixtures, hard-negative mining, synthetic augmentation, or preference datasets.

## **Choose Your Path**

- [x] Tabular ML dataset  
- [ ] Vision dataset  
- [ ] NLP dataset  
- [ ] LLM fine-tuning dataset  
- [ ] Ranking dataset  
- [ ] Recommender dataset  
- [x] RAG evaluation dataset

---

# **17\. Build Data Pipelines for RAG and Vector Search**

## **Core Checklist**

- [x] I can define:  
      - [x] Document ingestion  
      - [x] Parsing  
      - [x] Chunking  
      - [x] Embedding  
      - [x] Vector database  
      - [x] Metadata filter  
      - [x] Retrieval  
      - [x] Reranking  
      - [x] Grounding  
- [x] I can explain how documents become searchable chunks.  
- [x] I can build a basic RAG data pipeline.  
- [x] I can store chunks with metadata.  
- [x] I can retrieve relevant chunks for a user query.

## **Stretch Checklist**

- [x] I can diagnose retrieval failures caused by:  
      - [x] Poor parsing  
      - [x] Bad chunking  
      - [x] Missing metadata  
      - [x] Stale documents  
      - [x] Weak embeddings  
      - [x] Permission issues  
- [x] I can compare chunking strategies.  
- [x] I can design metadata-aware retrieval.  
- [x] I can design access-controlled RAG.  
- [x] I can design retrieval evaluation and monitoring.

## **Choose Your Path**

* Legal document RAG  
* Education content RAG  
* Company knowledge base RAG  
* Support ticket RAG  
* Codebase RAG  
* Research paper RAG  
* Medical document RAG

---

# **18\. Monitor Data, Drift, and Feedback Loops**

## **Core Checklist**

- [x] I can define:  
      - [x] Data drift  
      - [x] Concept drift  
      - [x] Label drift  
      - [x] Schema drift  
      - [x] Model drift  
      - [x] Feedback loop  
      - [x] Monitoring metric  
- [x] I can monitor:  
      - [x] Input distributions  
      - [x] Missing values  
      - [x] Category frequencies  
      - [x] Prediction distributions  
      - [x] Label delays  
      - [x] Data freshness  
- [x] I can explain how drift can reduce model performance.

## **Stretch Checklist**

- [x] I can distinguish between:  
      - [x] Natural seasonality  
      - [x] Real-world behavior change  
      - [x] Pipeline bugs  
      - [x] Harmful distribution shift  
- [x] I can decide when drift requires:  
      - [x] Investigation  
      - [x] Retraining  
      - [x] Rollback  
      - [x] Pipeline repair  
      - [x] Alert escalation  
- [x] I can design a monitoring dashboard for an AI data pipeline.

## **Paths to explore**

* Recommender system monitoring  
* Fraud model monitoring  
* Forecasting monitoring  
* LLM application monitoring  
* Educational AI monitoring  
* Computer vision monitoring

---

# **19\. Plan Data Retention, Archival, and Deletion**

## **Core Checklist**

- [x] I can define:  
      - [x] Retention policy  
      - [x] Archival  
      - [x] Deletion  
      - [x] Right to erasure  
      - [x] Cold storage  
      - [x] Legal hold  
      - [x] Lifecycle expiration  
- [x] I can explain why indefinite data retention creates:  
      - [x] Legal risk  
      - [x] Ethical risk  
      - [x] Security risk  
      - [x] Cost risk  
- [x] I can create a simple retention schedule for different data types.

## **Stretch Checklist**

- [x] I can identify deletion challenges involving:  
      - [x] Backups  
      - [x] Derived datasets  
      - [x] Embeddings  
      - [x] Logs  
      - [x] Trained models  
      - [x] Evaluation datasets  
- [x] I can design deletion workflows with audit logs.  
- [x] I can reason about machine unlearning and lineage-aware deletion.

## **Choose Your Path**

* User analytics retention  
* Education platform retention  
* Healthcare data retention  
* Financial data retention  
* LLM log retention  
* Enterprise search retention

---

# **Capstone project**

Choose one AI product idea evaluate entire Data lifecycle in the project

## **Project Options**

* AI learning assistant  
* Customer support RAG chatbot  
* Recommendation system  
* Fraud detection system  
* Student performance prediction system  
* Healthcare triage classifier  
* Document intelligence system  
* LLM evaluation platform  
* Computer vision inspection system  
* Forecasting and demand planning system  
* Your own AI system idea

## **Required Project Checklist**

* [ ] I selected one AI system.  
* [ ] I described the problem the system solves.  
* [ ] I identified the users and stakeholders.  
* [ ] I mapped the full data lifecycle.  
* [ ] I described the source systems.  
* [ ] I designed the data collection plan.  
* [ ] I designed the event schema or data schema.  
* [ ] I built or described the ingestion process.  
* [ ] I designed the storage architecture.  
* [ ] I created raw, cleaned, and curated data layers.  
* [ ] I cleaned and preprocessed the data.  
* [ ] I transformed the data into model-ready form.  
* [ ] I created features, chunks, embeddings, or labels as needed.  
* [ ] I wrote data validation checks.  
* [ ] I designed train/validation/test or evaluation datasets.  
* [ ] I documented dataset versions and metadata.  
* [ ] I described governance, privacy, and access control.  
* [ ] I designed a retention and deletion policy.  
* [ ] I designed monitoring and drift detection.  
* [ ] I explained the main trade-offs in my design.  
* [ ] I prepared a final technical report or walkthrough.

## **Strong Project Evidence**

Your final work should show that you can:

* **Remember** the major concepts and terminology.  
* **Understand** how lifecycle stages affect AI systems.  
* **Apply** Python, SQL, and data tools to lifecycle tasks.  
* **Analyze** quality issues, leakage risks, drift, and governance gaps.  
* **Evaluate** trade-offs around cost, latency, accuracy, privacy, and maintainability.  
* **Create** a complete lifecycle design for a realistic AI product.

## Final Self-Assessment before project submission

## **Conceptual Understanding**

* [x] I can explain the full data lifecycle without notes.  
* [x] I can explain why data quality matters for AI performance.  
* [x] I can explain how data moves from source systems to model training and production use.  
* [x] I can explain the role of governance, security, and deletion.

## **Practical Skills**

* [x] I can ingest data using Python or SQL.  
* [x] I can clean messy data.  
* [x] I can design schemas.  
* [x] I can create features or retrieval chunks.  
* [x] I can write validation checks.  
* [x] I can create model-ready datasets.  
* [x] I can track dataset versions.  
* [x] I can design monitoring checks.

## **Advanced Skills**

* [x] I can detect leakage.  
* [x] I can reason about drift.  
* [x] I can design point-in-time correct features.  
* [x] I can design RAG data pipelines.  
* [x] I can design data governance policies.  
* [x] I can design lineage and reproducibility systems.  
* [x] I can evaluate lifecycle trade-offs.

## **Portfolio Readiness**

* [ ] My project has a clear architecture diagram.  
* [ ] My project has clean code or clear technical specifications.  
* [ ] My project includes data quality checks.  
* [ ] My project includes governance and monitoring plans.  
* [ ] My project explains trade-offs clearly.  
* [ ] My project could be presented to a technical reviewer.
