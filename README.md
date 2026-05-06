# 📊 AI-Powered Variance Report Automation using n8n + Gemini

> Automate your daily data comparison and variance reporting with the power of AI, no code required.

---

## 📖 Project Overview

In teams where daily CSV data must be compared with live DB data, manual variance checking becomes repetitive and error-prone.

This project automates the full workflow using:
- 💌 Email input (CSV file)
- 🗃️ Postgres DB
- 🧠 Google Gemini (via AI Agent)
- 📝 Google Docs (for report creation)
- 📤 Gmail (to share the final report)

> The result? A complete variance report created and shared without lifting a finger.

---

[![Watch the Project](https://raw.githubusercontent.com/CB-AI-Toolkit-for-Professional/10.-P8-AI-Powered-Variance-Report-Automation-using-n8n-Gemini/main/Thumbnail.png)](https://www.youtube.com/watch?v=y6LRK9wCA8Y)

---

## 🎯 What This Automation Does

- Extracts CSV file from incoming email  
- Fetches matching data from Postgres database  
- Uses Gemini AI Agent to perform smart comparison  
- Identifies mismatch in:
  - Row counts
  - Column structure
  - Total values
  - City-level metrics  
- Creates a Variance Report in Google Docs  
- Shares the report link via Gmail  

---

## 🧰 Tools Used

| Tool             | Purpose                                 |
|------------------|------------------------------------------|
| **n8n**          | Workflow automation platform             |
| **Gmail**        | Receives CSV via email                   |
| **Postgres**     | Fetches reference system data            |
| **Google Gemini**| Compares datasets and writes markdown    |
| **Google Docs**  | Stores and formats final report          |
| **Google Drive** | Makes the document shareable             |

---

## 🧠 System Workflow

![Workflow Image](https://github.com/SachinSavkare/AI-Powered-Variance-Report-Automation-using-n8n-Gemini/blob/main/N8N%20Model.JPG)

---

## 📘 Beginner Guide

🔗 [Download Full Project Guide (PDF)](https://github.com/SachinSavkare/AI-Powered-Variance-Report-Automation-using-n8n-Gemini/blob/main/Project%20Guide.pdf)

---

## 📩 Sample Email Input

![Sample Email](https://github.com/SachinSavkare/AI-Powered-Variance-Report-Automation-using-n8n-Gemini/blob/main/Sample%20Mail.JPG)

---

## 🛠️ Step-by-Step Setup

### 1. **Email Trigger**
- Use Gmail trigger node to detect new emails with CSV.
- Extract CSV content.

### 2. **Fetch Old System Data**
- Use Postgres node.
- Fetch reference dataset with SQL query.

### 3. **AI Agent for Smart Comparison**
- Tool: Google Gemini via AI Agent node in n8n.

#### System Message Prompt:

```
You are an AI Agent in n8n.

Your task is to compare two datasets:
1. emailData (CSV from mail)
2. dbData (Postgres query)

You will:
- Compare total row counts
- Compare column counts and column names
- Compare total values of a numeric column (overall and per city)

You must return a VALID JSON OBJECT with this exact structure:
{ "docTitle": "...", "docBodyMarkdown": "...", "summary": "...", "overallVariance": {...}, "cityVariance": [...] }

❗ IMPORTANT:
- DO NOT output any explanation or extra text.
- Return only the JSON object in the exact format.
```

---

### 4. **Prepare Data for AI Input**
- Use `Aggregate` + `Edit Fields` nodes to convert array into clean string.

---

### 5. **Generate Report in Google Docs**
- Create Google Doc.
- Insert AI-generated markdown into the document.

---

### 6. **Share and Notify**
- Share the doc via Google Drive (public link).
- Send the link back via Gmail response.

---

## ✅ Benefits

- Automates entire variance checking process  
- Saves hours of repetitive work  
- Generates consistent reports  
- Uses AI for smart, explainable comparison  
- 100% no-code using n8n + Gemini

---

## 📂 Files Included in Repo

| File                     | Description                            |
|--------------------------|----------------------------------------|
| `N8N Model.JPG`          | Visual workflow diagram                |
| `Guide_VarianceReport.pdf` | Step-by-step setup guide (PDF)        |
| `Sample Mail.JPG`        | Input mail with CSV sample             |
| `Prompts.docx`           | System messages and structured prompts |

---

## 👨‍💻 Built By

**Sachin Savkare**  
AI + Automation Enthusiast  
🔗 [Connect on LinkedIn](https://www.linkedin.com/in/sachin-savkare)

---

## 📎 License

This project is licensed under the **MIT License**.

