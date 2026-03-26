# 🏦 LoanIQ - AI Loan Eligibility Checker

![LoanIQ Banner](https://img.shields.io/badge/LoanIQ-AI_Eligibility_Checker-C9A84C?style=for-the-badge)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Node.js](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white)
![Dialogflow](https://img.shields.io/badge/Dialogflow-FF9800?style=for-the-badge&logo=dialogflow&logoColor=white)

LoanIQ is an intelligent, real-time chatbot application designed to evaluate loan approval probabilities. By engaging users in a natural, 10-step conversation, LoanIQ gathers financial data and processes it through a custom-built, multi-factor scoring algorithm to determine creditworthiness instantly.

---

## 🚀 Features

- **Interactive AI Chatbot:** Replaces static, boring finance forms with a dynamic conversational interface powered by Google Dialogflow.
- **Custom Scoring Engine:** Evaluates 8 critical financial parameters (including Credit Score, DTI ratio, Income, and Loan Purpose) to calculate an accurate eligibility score.
- **Instant Result Generation:** Provides immediate feedback, including an estimated EMI, Debt-to-Income (DTI) ratio, a percentage-based eligibility score, and a final verdict.
- **Actionable Financial Tips:** If your eligibility is low, the engine conditionally provides actionable, personalized tips to improve your approval odds before applying to real lenders.
- **Premium UI/UX:** Built from scratch with vanilla HTML/CSS/JS, featuring glassmorphism, dynamic SVG backgrounds, auto-scrolling chat, and animated scoring bars.
- **Decoupled Architecture:** A completely isolated frontend proxying requests to a secure Express.js webhook backend.

---

## 🛠️ Technology Stack

**Frontend (Client)**
- **HTML5 & CSS3:** Custom-built responsive UI with CSS variables, modern grid/flexbox layouts, and keyframe animations.
- **Vanilla JavaScript:** Fast, lightweight DOM manipulation, user input validation, and asynchronous API calls.

**Backend (Server)**
- **Node.js & Express:** Lightweight, fast REST API to proxy requests and serve Dialogflow fulfillment webhooks.
- **Google Dialogflow (NLP):** Natural Language Processing to detect user intent and manage the conversation flow.
- **Render:** Cloud hosting for the webhook server, featuring automated health checks to prevent cold starts.

---

## 💡 How The Scoring Model Works

The custom scoring model simulates real-world banking risk assessment by assigning weighted point values to 8 key factors (Max Score = 100):

1. **Credit Score (30%)** - CIBIL scoring tiers.
2. **Debt-to-Income Ratio (25%)** - Calculates total obligations (existing EMI + proposed EMI) against total household income.
3. **Income vs Loan Amount (20%)** - Evaluates if the requested loan is within safe lending multiples.
4. **Employment Type (10%)** - Stability tiers (Government > Private > Self-Employed > Freelance).
5. **Age & Demographics (5%)** - Maximum allowable tenure constraints based on retirement age.
6. **Loan Purpose (5%)** - Asset-backed loans (Home/Vehicle) receive higher priority than unsecured personal loans.
7. **Dependents (3%)** - Adjusts implied disposable income.
8. **Property Area (2%)** - Tier classification based on geographical location.

Based on the total sum, the engine outputs one of 5 verdicts ranging from **"Strong Approval Likely"** to **"High Rejection Risk"**, dynamically generating a markdown-style report in the chat window.

---

## 📖 System Architecture

1. **User Input:** The user sends a message via the Custom Frontend UI.
2. **Proxy Request:** The frontend securely POSTs the message and a unique session ID to the custom Express backend (`/chat` endpoint).
3. **Intent Detection:** The backend forwards the request securely to Google Dialogflow using the Dialogflow SDK (hiding all Google Service Credentials from the client).
4. **Fulfillment Webhook:** If Dialogflow determines the conversation is complete (i.e., gathering the final parameter), it calls the `/webhook` endpoint on the backend.
5. **Algorithmic Evaluation:** The backend extracts the context parameters, runs the Loan Eligibility Engine calculation, and returns the formatted result safely back through the chain to the UI.

---

## 👨‍💻 About The Developer

*This project was developed to demonstrate full-stack engineering capabilities, UI/UX design, algorithmic problem solving, and third-party API integration.*

- Find me on [LinkedIn](#) *(Replace with your URL)*
- Check out my other projects on [GitHub](#) *(Replace with your URL)*
