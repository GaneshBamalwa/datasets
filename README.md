# Financial FAQ Structured Dataset for Indian Financial AI Assistants

A curated, schema-driven dataset created from official financial FAQs, regulatory guidance, investor awareness documents, banking FAQs, government scheme documentation, insurance FAQs, and cyber-fraud awareness material.

The dataset is designed for training, evaluation, benchmarking, retrieval systems, instruction tuning, and financial question-answering applications focused on Indian users.

---

# Overview

This dataset converts unstructured financial FAQ documents into structured JSON records.

Each record represents **exactly one user intent** and follows a standardized schema to ensure:

- Consistency
- Regulatory accuracy
- Easy machine consumption
- Better retrieval quality
- Improved LLM fine-tuning performance

The dataset covers multiple domains of financial literacy and consumer awareness in India.

---

# Supported Domains

## 1. Banking & Digital Payments

Examples:

- UPI
- IMPS
- NEFT
- RTGS
- Debit Cards
- Credit Cards
- ATM Services
- Savings Accounts
- KYC Requirements
- Demat Accounts
- Trading Accounts
- Stock Brokers

## 2. Government Schemes

Examples:

- PMJDY
- PMSBY
- PMJJBY
- APY
- NPS
- KCC
- SHG Schemes
- Government Financial Inclusion Programs

## 3. Fraud and Cyber Security

Examples:

- OTP Fraud
- Phishing
- QR Code Scams
- KYC Fraud
- Investment Scams
- Digital Payment Frauds
- Social Engineering Attacks

## 4. Savings and Insurance

Examples:

- Mutual Funds
- Fixed Deposits
- Life Insurance
- Health Insurance
- Pension Products
- ETFs
- ELSS
- SIP
- STP
- SWP
- Retirement Schemes

## 5. Credit and Borrowing

Examples:

- Personal Loans
- Home Loans
- Gold Loans
- Education Loans
- Microfinance
- Credit Scores
- Lending Products

---

# Dataset Schema

Each record follows the structure below:

```json
{
  "user_query": "",
  "domain_category": "",
  "subdomain": "",
  "user_profile": null,
  "answer_guidance": "",
  "actions_suggestions_next_step": [],
  "learning_outcome": "",
  "feedback": null
}
```

---

# Field Definitions

## user_query

Natural language question representing a single user intent.

Example:

```json
"What is a Mutual Fund?"
```

## domain_category

One of:

```text
Banking & Digital Payments
Government Schemes
Fraud and Cyber Security
Savings and Insurance
Credit and Borrowing
```

## subdomain

More specific topic classification.

Examples:

```text
UPI
Mutual Funds
KCC
OTP Fraud
PMJDY
Life Insurance
Personal Loan
Demat Account
Stock Broker
```

## user_profile

Optional metadata describing the intended audience.

Example:

```json
{
  "age_group": "Senior Citizen",
  "literacy_level": "Basic",
  "location_type": "Rural"
}
```

If audience information is not explicitly provided in the source:

```json
null
```

## answer_guidance

A factual and neutral answer derived strictly from the source material.

Requirements:

- Preserve regulatory accuracy.
- Preserve eligibility criteria.
- Preserve procedural steps.
- Preserve numerical thresholds.
- Avoid recommendations or financial advice.
- Avoid hallucinations.

## actions_suggestions_next_step

A list of safe educational next steps.

Example:

```json
[
  "Review the official eligibility criteria.",
  "Refer to the relevant regulatory guidance document.",
  "Read the official application process before applying."
]
```

## learning_outcome

A concise statement describing what the user learns.

Examples:

```text
User understands how a UPI transaction works.
User learns the eligibility criteria for PMJDY.
User is able to identify signs of OTP fraud.
```

## feedback

Always:

```json
null
```

for FAQ-derived records.

---

# Dataset Generation Principles

### One Intent = One Record

Each JSON object must correspond to exactly one user question or intent.

**Correct**

- What is SIP?
- What is STP?
- What is SWP?

Three separate records.

**Incorrect**

Combining all three into a single record.

---

### Preserve Regulatory Information

Always retain:

- Percentages
- Monetary limits
- Eligibility criteria
- Age requirements
- Lock-in periods
- Time limits
- Contribution requirements

Example:

```text
Minimum investment: ₹500
```

should never become

```text
Small minimum investment
```

---

### Preserve Official Acronyms

Keep official terms unchanged:

- RBI
- SEBI
- NPCI
- UPI
- PMJDY
- PMSBY
- PMJJBY
- APY
- NPS
- KCC
- SHG
- OTP
- KYC
- ATM

---

### No Hallucination Policy

The dataset follows a strict source-grounded approach.

Do not invent:

- Eligibility conditions
- Benefits
- Procedures
- Contact details
- Penalties
- Timelines

If information is unavailable, it is omitted.

---

# Intended Use Cases

This dataset can be used for:

- Financial AI Assistants
- Retrieval-Augmented Generation (RAG)
- FAQ Search Systems
- Intent Classification
- Domain Classification
- Fine-Tuning Language Models
- Instruction-Tuning Datasets
- Evaluation Benchmarks
- Financial Literacy Applications
- Government Service Chatbots
- Banking Support Assistants

---

# Data Quality Standards

Every record is:

- Source-grounded
- Single-intent
- Schema-compliant
- Regulation-aware
- Human-readable
- Machine-readable

The dataset prioritizes accuracy, consistency, and educational value over conversational style.

---

# Disclaimer

This dataset is intended solely for educational, research, benchmarking, and AI development purposes.

The content is derived from publicly available financial FAQs, regulatory guidance, investor education material, and official documentation.

The dataset does **not** provide investment advice, legal advice, tax advice, or lending recommendations.

Users should refer to the relevant regulator, financial institution, or official source for authoritative and up-to-date information.

---

# License

Specify your preferred license here.

Examples:

- MIT License
- Apache 2.0
- CC BY 4.0
- CC BY-SA 4.0

---

# Citation

If you use this dataset in research or production systems, please cite the repository and acknowledge the original regulatory and educational sources from which the structured records were derived.