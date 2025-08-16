# PRD: Project Athena - The Reactive Assistant (MVP)

* **Status:** In Development
* **Author:** Jeremy Bailey
* **Last Updated:** August 16, 2025
* **Related Docs:** [Project Roadmap](./Roadmap.png), [User Research](./../research/), [Design Wireframes](./../designs/)

---

## 1. The Big Picture

### 1.1. Problem Statement

Sales representatives, our primary CRM users, are burdened by administrative tasks, spending an estimated **8-10 hours per week** on non-selling activities like data entry and research. This significantly reduces their productivity and morale. Furthermore, critical customer insights are often fragmented across disparate sources (emails, call logs, past deals), making it difficult for reps to prepare for calls effectively. Our own data shows that **40% of sales opportunities are missing key fields**, leading to inaccurate forecasting and missed revenue targets.

The CRM, intended to be a single source of truth, has become a complex chore rather than a strategic tool.

### 1.2. Product Vision & Goal

Our long-term vision is to **transform our CRM from a passive system of record into a proactive system of intelligence** that works for the seller.

The goal of this MVP, "The Reactive Assistant," is to validate our core hypothesis: **that a conversational AI assistant can significantly reduce the time reps spend searching for information and generating routine content.** We will build user trust by delivering a reliable and fast Q&A and content generation experience integrated directly into the CRM.

### 1.3. Target Audience

This MVP will focus on two primary user personas:

* **Alex, the Account Executive (AE):** The primary user who will leverage Athena daily to get answers, prepare for meetings, and draft communications.
* **Maria, the Sales Manager:** A secondary user who benefits from the improved data quality and can use Athena for quick pipeline analysis.

---

## 2. Measuring Success

### 2.1. North Star Metric

Our North Star metric is **Weekly Interacting Users (WIU)**. We define an "interaction" as a user receiving a successful response from Athena. This metric captures both adoption and recurring value.

### 2.2. Product & Business KPIs

We will measure the success of the MVP against the following key performance indicators.

| Metric | Description | Target (First 90 Days) |
| :--- | :--- | :--- |
| **Adoption Rate** | % of eligible AEs who use Athena at least once per week. | `> 30%` |
| **Task Success Rate** | % of queries that do not result in a "Sorry, I can't help with that" response. | `> 85%` |
| **Average Query Time** | Time from query submission to receiving a full response from the AI. | `< 3 seconds` |
| **Qualitative Feedback (CSAT)** | User satisfaction score gathered via an in-app survey after 10 queries. | `> 4.0 / 5.0` |
| **Time Spent on CRM Pages** | **(Counter Metric)** We will monitor this to ensure Athena doesn't make the CRM more complex. | `No significant increase` |

---

## 3. User Scenarios & Requirements

These requirements define the core functionality for the MVP. They are framed as user stories, grouped into epics.

### Epic 1: Conversational Q&A

*As an Account Executive, I want to ask questions about my data in natural language so that I can get information quickly without navigating complex dashboards or reports.*

| User Story ID | User Story | Acceptance Criteria |
| :--- | :--- | :--- |
| **ATH-01** | As Alex, I want to ask "Who is the primary contact for Acme Corp?" to get the contact's name, title, and email. | - System correctly identifies "Acme Corp" as the account.<br>- Response provides the contact marked as "Primary."<br>- Response includes name, title, email, phone. |
| **ATH-02** | As Alex, I want to ask "What is the status of Opportunity #12345?" to get the deal stage, amount, and next steps. | - System retrieves the correct opportunity.<br>- Response includes Stage, Amount, Expected Close Date, and the content of the "Next Steps" field. |
| **ATH-03** | As Alex, I want to ask "Summarize my last call with Globex Inc." to get a bulleted list of key discussion points. | - System finds the most recent call log associated with the "Globex Inc" account.<br>- Response is a concise, AI-generated summary (3-5 bullet points). |

### Epic 2: Content Generation

*As an Account Executive, I want to generate routine sales content so that I can save time on writing and focus on personalizing my outreach.*

| User Story ID | User Story | Acceptance Criteria |
| :--- | :--- | :--- |
| **ATH-04** | As Alex, I want to ask "Draft a follow-up email to Jane Doe at Acme Corp about our call yesterday." | - System identifies the context (Jane Doe, Acme Corp, last call).<br>- Generates a professional email draft including a greeting, summary of the call, and a call to action.<br>- Includes a "Copy to Clipboard" button. |
| **ATH-05** | As Alex, I want to be able to refine the generated draft by giving a follow-up command like "Make it shorter." | - The conversation history is maintained.<br>- The system regenerates the email based on the new instruction, making it more concise. |

---

## 4. Go-to-Market Plan

This will be a phased internal rollout to gather feedback and ensure stability before a wider release.

1.  **Internal Alpha (Eng & Product):** Continuous testing by the core team.
2.  **Closed Beta (Pilot Sales Team):** Rollout to a hand-picked team of 10-15 high-performing AEs who have opted-in. We will collect intensive qualitative feedback during this phase.
3.  **General Availability (GA):** Full rollout to all customer-facing sales roles. This will be accompanied by an internal marketing campaign and training sessions.

**Dependencies:**
* **Legal & Security:** Review of data handling practices, especially regarding the LLM provider's data privacy policies.
* **Sales Enablement:** Development of training materials for the sales team.

---

## 5. Scope

### 5.1. In Scope for MVP

* A chat-based interface accessible from the main CRM dashboard.
* Ability to answer queries about Accounts, Contacts, and Opportunities.
* Ability to summarize the most recent call log for an account.
* Generation of follow-up email drafts.
* Conversation history within a single session.

### 5.2. Out of Scope for MVP

* **Proactive features:** Athena will **not** initiate conversations or send notifications.
* **Actions/Workflow automation:** Athena will **not** update any CRM records. All actions are informational.
* **Advanced analytics:** Complex queries like "Show me all deals that are at risk" are out of scope.
* **Multi-language support:** The MVP will be English-only.
* **Mobile app integration:** The MVP will be desktop-only.

---

## 6. Open Questions & Risks

* **Technical Risk:** The accuracy of the LLM in summarizing call notes can vary. We need a robust testing framework to measure and improve summary quality.
* **User Trust:** How do we handle situations where Athena is wrong or can't find an answer? The UX for these "failure states" is critical for building long-term user trust.
* **Performance:** Can we consistently meet the `< 3 second` response time target during peak usage hours?
* **Data Privacy:** How do we ensure no PII (Personally Identifiable Information) is inadvertently retained by our third-party LLM provider? A clear data anonymization strategy may be required.