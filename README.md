# 🤖 AI-Augmented Test Automation  
### From Script Execution to Intelligent Test Maintenance

This project demonstrates how to augment traditional test automation using Playwright with AI-assisted techniques to improve debugging, reduce maintenance effort, and identify test gaps.

---

## 🚀 Overview

Modern test automation frameworks like Playwright are excellent at execution and reporting, but they lack intelligence in:

- Identifying root causes of failures  
- Suggesting fixes  
- Highlighting missing test coverage  

This project introduces a **lightweight AI-augmented layer** that transforms automation into a **decision-support system**.

---

## 🧠 Key Capabilities

### ✅ Failure Intelligence
- Captures structured failure context  
- Analyzes error, locator, and DOM  
- Classifies failure type  
- Suggests actionable fixes  

---

### ✅ Locator Resilience
- Identifies brittle locators  
- Suggests stable alternatives  
- Promotes strategy-based selectors  

---

### ✅ Coverage Insights
- Highlights missing test scenarios  
- Identifies gaps in validation  
- Supports better test design  

---

### ✅ Human-in-the-Loop
- AI suggests, engineers validate  
- No automatic test modification  
- Ensures reliability and control  

---

## 🏗️ Architecture
Playwright Test Execution
↓
Failure Context Capture (JSON)
↓
AI Analyzer (Mock / Real)
↓
Actionable Insights
↓
Human Validation & Fix

---

## 📁 Project Structure
ai-automation-demo/
├── tests/

│ └── login.test.ts
├── utils/
│ ├── failureCollector.ts
│ └── aiAnalyzer.ts
├── scripts/
│ └── analyze.ts
├── public/
│ ├── login.html
│ └── secure.html
├── artifacts/
│ └── failure-context.json
├── playwright.config.ts
├── package.json
└── tsconfig.json


---

## ⚙️ Setup Instructions

### 1️⃣ Install dependencies

```bash
npm install

2️⃣ Install Playwright browsers
```bash
npx playwright install

▶️ How to Run the Demo

🔹 Step 1 — Run test (intentional failure)
```bash
npm run test
👉 This will:

Execute login test
Fail due to incorrect locator
Generate failure context

🔹 Step 2 — View failure context

Open:
artifacts/failure-context.json
Example:
{
  "error": "locator.click: Test timeout...",
  "locator": "#loginBtn",
  "url": "file:///...",
  "dom": "DOM not available"
}
{
  "error": "locator.click: Test timeout...",
  "locator": "#loginBtn",
  "url": "file:///...",
  "dom": "DOM not available"
}
🔹 Step 3 — Run AI analysis
npm run analyze

Example output:

{
  "failure_type": "LOCATOR_CHANGED",
  "root_cause": "loginBtn does not exist. Actual ID is submitBtn",
  "suggested_fix": "#submitBtn"
}
🔹 Step 4 — Fix the test

Update locator:

await page.locator('#submitBtn').click();

OR use resilient locator:

await page.locator('button:has-text("Login")').click();
🔹 Step 5 — Re-run test
npm run test

👉 Result:

1 passed

🎯 Demo Flow Summary
Test fails due to locator issue
Failure context is captured
AI analyzes the failure
Root cause and fix are identified
Test is updated and passes

💡 Key Takeaways
Move from execution → intelligence
Reduce debugging time
Improve test stability
Identify missing coverage
Maintain human control

⚠️ Notes
This demo uses a mock AI analyzer for stability
Can be extended with real AI APIs
Fully offline-capable for reliable demos

🔮 Future Enhancements
Real AI API integration
Automated test suggestion system
CI/CD integration
Visual dashboard for insights

👩‍💻 Author

Santhana Lakshmi
AI-Augmented Test Automation Workshop

⭐ If you found this useful

Give this repo a ⭐ and share with your team!
