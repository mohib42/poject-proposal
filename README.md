💰 AI-Powered Personal Finance Assistant

Expense analysis · Budget planning · Savings prediction · Financial chatbot

Show Image Show Image Show Image Show Image

Software Engineering Project Proposal and Prototype Department of ICT, Mawlana Bhashani Science and Technology University (MBSTU)

</div>
📌 Overview

Many students and young professionals track their money in notebooks, in memory, or through mobile-wallet histories (bKash, Nagad, Rocket) and rarely analyse where it goes. AI-PFA turns raw income and expense records into clear insight:

where the money goes,
whether the user is staying within budget,
how much they are likely to save next month,
and answers to everyday money questions in plain language.

This repository contains the full project proposal (requirements, process model, schedule, UML models) and a working prototype built from the classes in the class diagram.

✨ Features
Feature	Description	Prototype status
Transaction tracking	Record income and expenses by category	✅ Implemented
Expense analysis	Spending by category and by month	✅ Implemented
Anomaly detection	Flags unusually large expenses (z-score rule)	✅ Implemented
Budgets	Monthly category limits with OK / WARNING / OVER status	✅ Implemented
Savings prediction	Next-month savings via least-squares linear trend	✅ Implemented
Financial chatbot	Intent-based answers about spending, budget and savings	✅ Implemented (rule-based)
Savings goals	Targets with progress tracking	🕓 Planned (Sprint 2)
User accounts and database	Login, persistent storage (SQLite/PostgreSQL)	🕓 Planned (Sprint 1)
ML upgrades	Random Forest / ARIMA, Isolation Forest, auto-categorisation	🕓 Planned (Sprint 3)
CSV import and PDF reports	Bulk entry and export	🕓 Planned

Note: the prototype uses built-in sample data and a rule-based chatbot. The machine-learning and database features listed as planned are part of the proposal and are not in the current code.

🧩 Prototype Architecture

The prototype follows the proposal's class diagram:

FinanceApp (Tkinter GUI)
   ├── FinanceChatbot ───► ExpenseAnalyzer ───► Transaction ──► Category
   │          │                    ▲
   │          ├──► SavingsPredictor ┘
   │          └──► Budget ──► Category
   └── User
Class	Responsibility
User	Account holder and monthly income
Category	Income or expense category
Transaction	One income/expense record
Budget	Monthly limit per category and its status
ExpenseAnalyzer	Totals by category/month, anomaly detection
SavingsPredictor	Linear-regression forecast of next-month savings
FinanceChatbot	Detects the user's intent and answers from their data
FinanceApp	Tkinter interface (Dashboard, Add Transaction, Chatbot)
🚀 Getting Started
Requirements
Python 3.9 or newer
Tkinter (included with most desktop Python installs) for the GUI
No third-party packages needed
Run
bash
# Graphical interface
python finance_assistant.py

# Console demo (no GUI needed)
python finance_assistant.py --demo
Example demo output
> Where did I spend most?
You spent 20,000 BDT this month; highest: Rent (8,000).
> Show my budget
Food: 6,000/6,500 [WARNING]
Fun: 1,500/1,200 [OVER]
> Predict next month savings
Predicted savings next month: 10,600 BDT.
Try these chatbot questions
"Where did I spend most this month?"
"Show my budget"
"Predict next month savings"
"Give me a tip"
🗓️ Project Plan

Process model: Incremental Model with Scrum-style 3-week sprints Duration: 16 weeks (2 Nov 2026 – 21 Feb 2027)

Phase	Weeks	Focus
Planning and requirements	1–2	Feasibility, SRS, use cases
Design	3–4	UML models, database schema, UI wireframes
Sprint 1	5–7	Accounts, transactions, categories
Sprint 2	8–10	Analytics, budgets, goals
Sprint 3	11–13	Prediction model, chatbot
Testing	14–15	Integration, system and usability tests
Release	15–16	Deployment, documentation, final demo

7 milestones (M1–M7) and 10 deliverables (D1–D10) are defined in the proposal, together with a Gantt chart, risk register and test plan.

📐 UML Models Included

The proposal contains six diagrams, drawn in TikZ:

Data Flow Diagram (Level 0 and Level 1)
Use Case Diagram
Activity Diagram
Entity-Relationship Diagram
Class Diagram
Object Diagram
🛠️ Technology Stack
Layer	Technology
Language	Python 3
Prototype UI	Tkinter
Planned backend	Flask or FastAPI
Planned database	SQLite (development), PostgreSQL (deployment)
Planned ML	pandas, NumPy, scikit-learn
Documentation	LaTeX (TikZ, pgfgantt)
📁 Repository Structure
.
├── README.md                                   ← this file
├── finance_assistant.py                        ← prototype (GUI + console demo)
├── main.tex                                    ← LaTeX source of the proposal
└── AI_Finance_Assistant_Proposal_IT24058.pdf   ← compiled proposal (20 pages)
Rebuild the proposal PDF

Upload main.tex and finance_assistant.py to the same Overleaf project (or the same local folder) and compile with pdfLaTeX. The Python file is included in the report as a source listing, so both files must be present.

🔭 Future Work
Connect to bKash/Nagad/bank statements
Receipt scanning (OCR)
Bangla-language chatbot
Mobile application
Personalised saving-plan recommendations
👤 Author

MD. MOHIB HASAN Student ID: IT24058 Department of Information and Communication Technology (ICT) Mawlana Bhashani Science and Technology University (MBSTU), Santosh, Tangail

Supervisor: Prof. Dr. Ziaur Rahaman, Department of ICT, MBSTU

📚 References
I. Sommerville, Software Engineering, 10th ed., Pearson, 2016.
R. S. Pressman and B. Maxim, Software Engineering: A Practitioner's Approach, 9th ed., McGraw-Hill, 2020.
M. Fowler, UML Distilled, 3rd ed., Addison-Wesley, 2003.
F. Pedregosa et al., "Scikit-learn: Machine Learning in Python," JMLR, 12, 2011.
