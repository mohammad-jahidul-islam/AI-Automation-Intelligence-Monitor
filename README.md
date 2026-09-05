# AI & Automation Intelligence Monitor

> An AI-powered business intelligence workflow that automatically monitors industry news, removes duplicate information, identifies important developments, stores structured intelligence, and delivers a prioritised email briefing.

---

## 🔴 The Business Pain

Businesses need to keep track of important developments in their industry — competitors, new technologies, regulations, products, suppliers, market changes, and emerging opportunities.

The problem is that this information is spread across many different sources and new content appears continuously.

A typical employee may have to:

- Visit multiple industry websites and news sources
- Scan dozens of new articles
- Open and read articles individually
- Decide which information is actually relevant
- Ignore repeated or duplicate stories
- Identify companies and topics mentioned
- Summarise important developments
- Record useful information somewhere
- Prepare an update for managers or colleagues

### Why this becomes a business problem

Most of the information collected is not equally important.

Employees can spend significant time **searching and filtering information before they even reach something useful**.

This creates several problems:

- Repetitive manual research
- Information overload
- Important developments can be missed
- Duplicate information gets reviewed repeatedly
- Research quality depends on who performs it
- Useful intelligence may not be stored systematically
- Managers receive information late or inconsistently
- Staff time is spent collecting information instead of acting on it

The real problem is therefore not a lack of information.

**The problem is turning a large amount of incoming information into a small amount of useful, prioritised business intelligence.**

---

## 💡 My Solution

I built an **AI & Automation Intelligence Monitor** that automates this research and reporting process.

Instead of an employee manually checking, reading, filtering and summarising every article, the system:

1. Collects new industry articles automatically
2. Cleans and standardises the incoming data
3. Generates a unique fingerprint for each article
4. Checks PostgreSQL to detect previously processed content
5. Removes duplicate articles from further processing
6. Sends new articles for AI analysis
7. Identifies the company and category
8. Generates a relevance score
9. Creates a concise business summary
10. Stores analysed intelligence in PostgreSQL
11. Filters articles using a relevance threshold
12. Combines the most important developments
13. Generates an intelligence briefing
14. Delivers the report by email

This changes the process from:

**Find → Read → Compare → Filter → Summarise → Record → Report**

into:

**Automated Monitoring → Prioritised Intelligence → Business Action**

---

## 📈 Business Benefits

### Less Manual Research

Employees no longer need to manually inspect every incoming article. The workflow performs the first stage of research automatically.

### Reduced Information Overload

AI relevance scoring helps separate potentially important developments from lower-value information.

### Duplicate Prevention

Article fingerprints and PostgreSQL checks prevent the same content from being repeatedly processed.

This can also reduce unnecessary AI processing.

### Faster Access to Important Information

Relevant developments are automatically identified and included in an intelligence briefing.

### Consistent Analysis

Every article follows the same analysis process rather than depending entirely on different employees' judgement or available time.

### Searchable Intelligence History

Analysed articles are stored in PostgreSQL with structured information such as:

- Company
- Category
- Relevance score
- Summary
- Source
- Publication information

This creates a reusable intelligence dataset rather than allowing useful research to disappear inside emails or browser tabs.

### Better Use of Employee Time

The system handles repetitive information processing so employees can spend more time evaluating developments, making decisions and taking action.

---

## ⚙️ How It Works
```text

Industry / News Sources
          ↓
     RSS Collection
          ↓
  Normalise Article Data
          ↓
 Generate Article Fingerprint
          ↓
 PostgreSQL Duplicate Check
          ↓
       New Article?
          ↓
   Limit AI Processing
          ↓
     AI Analysis
          ↓
 Company + Category + Summary
      + Relevance Score
          ↓
   Save to PostgreSQL
          ↓
  Relevance Score ≥ 70?
          ↓
 Aggregate Relevant Articles
          ↓
 Generate Intelligence Brief
          ↓
      Email Report

```
### Example

Instead of an employee reviewing 15 incoming articles manually, the workflow can collect them automatically, reject previously processed content, analyse selected new articles and forward only sufficiently relevant information into the final intelligence report.

---

## 🎥 Demo

A short demonstration of the complete automation workflow is available below.

The demo shows the system:

- Collecting industry articles automatically
- Checking for duplicate content
- Analysing new articles with AI
- Assigning company, category and relevance score
- Filtering articles based on relevance
- Storing structured intelligence in PostgreSQL
- Generating the final intelligence briefing
- Delivering the report by email

### Demo Video

🎬 **60–90 second workflow demonstration:** Coming soon

### Screenshots

Screenshots of the workflow, AI analysis, duplicate detection, PostgreSQL storage and final email report are available in the `screenshots` folder.

---

## 🛠️ Technology

| Technology | Purpose |
|---|---|
| n8n | Workflow orchestration and automation |
| OpenAI API | Article analysis, relevance scoring, summarisation and intelligence report generation |
| PostgreSQL | Structured intelligence storage and duplicate detection |
| RSS | Automated collection of industry/news articles |
| Gmail | Automated delivery of intelligence reports |
| Docker | Local containerised environment for n8n and PostgreSQL |


---

## 🔧 Technical Details

### Workflow Stages

1. **Fetch AI & Automation News**  
   Collects incoming articles from configured RSS sources.

2. **Normalise Article Data**  
   Converts incoming RSS data into a consistent structure for downstream processing.

3. **Generate Article Fingerprint**  
   Creates a unique fingerprint that can be used to identify previously processed articles.

4. **Check for Duplicate Article**  
   Queries PostgreSQL to determine whether the article fingerprint already exists.

5. **Is New Article?**  
   Allows new content to continue while preventing duplicate content from being unnecessarily processed again.

6. **Limit Articles for AI Analysis**  
   Controls how many new articles are sent to the AI model, helping control API usage and processing cost.

7. **Analyse Article Relevance with AI**  
   Extracts structured intelligence including company, category, relevance score and summary.

8. **Save Analysed Article to PostgreSQL**  
   Stores the analysed article and its structured intelligence for future reference.

9. **Is Relevance Score ≥ 70?**  
   Filters the analysed information so only sufficiently relevant articles continue to the reporting stage.

10. **Aggregate Relevant Articles**  
    Combines qualifying articles into a single dataset.

11. **Generate Intelligence Brief**  
    Uses AI to transform the selected developments into a concise business intelligence report.

12. **Email Intelligence Report**  
    Automatically delivers the completed briefing through Gmail.

### Example Data Stored

```text
Title
Description
URL
Source
Published Date
Clean Text
Fingerprint
Company
Category
Relevance Score
Summary
Created At
```

### Duplicate Detection

Each article receives a fingerprint before AI analysis.

PostgreSQL checks whether that fingerprint already exists. Previously processed content can therefore be stopped before additional AI processing occurs.

This design helps prevent repeated analysis and unnecessary API usage.

### Relevance Filtering

The current workflow uses a relevance threshold of:

```text
Relevance Score >= 70
```

Articles meeting the threshold can proceed into the final intelligence briefing, while lower-scoring articles do not need to be included in the management report.

---

## 🏢 Potential Business Use Cases

The same workflow architecture could be adapted for different business monitoring requirements, including:

- Competitor monitoring
- Technology and product monitoring
- Regulatory and compliance updates
- Supplier and industry monitoring
- Market intelligence
- Customer or sector news monitoring
- Tender and opportunity monitoring
- Company-specific news alerts
- Research intelligence
- Internal management briefings

The data source, AI analysis criteria, relevance rules and reporting format can be customised for the organisation's requirements.

---

## 👤 Project Purpose

This project was built as a practical business automation portfolio project demonstrating how AI, workflow automation, APIs and databases can be combined to reduce repetitive information-processing work and turn unstructured incoming information into actionable business intelligence.
