# Curely — Connected Multi-Hospital Clinical & Patient Portal

> An intelligent, connected healthcare platform that unifies patient health records across multiple hospitals, simplifies doctor workflows, provides doctor-approved AI insights, and offers granular patient privacy controls.

---

## 🌟 The Problem We Solve

In modern healthcare:

1. **Siloed Patient Data:** Patients who visit different hospitals or clinics end up with scattered records, duplicate lab tests, and conflicting prescriptions because healthcare systems don't communicate.
2. **Medical Jargon & Anxiety:** Patients receive complex lab reports and diagnoses they struggle to understand, leading to confusion and unnecessary stress.
3. **Physician Documentation Burden:** Doctors waste valuable consultation time hunting down previous hospital visits, sorting test results, and managing unorganized queues.
4. **All-or-Nothing Family Sharing:** Elderly or dependent patients often need family support, but current portals lack the ability to share only select records while keeping sensitive health details private.

---

## 💡 What is Curely?

**Curely** bridges the gap between patients, doctors, and hospitals:

- **For Patients:** A single, centralized home for health records across every hospital visited, with clear timelines, plain-language AI explanations, direct doctor messaging, and custom family sharing permissions.
- **For Doctors:** A fast, focused clinical portal searchable by Social Security Number (SSN), organized by Pending and Done queues, with cross-hospital medical histories and AI-drafted assistance that requires physician review and approval.
- **For Hospitals:** A collaborative ecosystem where doctors at different facilities can coordinate care, prevent adverse drug interactions, and eliminate redundant testing.

---

## 🚀 Key Features

### 1. Unified Multi-Hospital Health Records

- Patients view an aggregated, chronological timeline of diagnoses, prescriptions, and lab findings from all participating clinics and hospitals.
- Hospital-specific badges make it immediately clear which clinic issued each prescription or conducted each test.
- Filter the care timeline by individual hospital or view all combined.

### 2. Streamlined Doctor Portal

- **SSN & Name Lookup:** Quickly pull up a patient's complete multi-hospital chart.
- **Pending vs. Done Queues:** Clearly tracks which patients need active review and which have completed their visits.
- **Clinical Actions:** Prescribe medications, log formal diagnoses, review lab findings, and undo or correct entries with full audit trails.
- **Per-Clinician Ownership:** Multi-doctor safety ensures each physician only edits or removes their own hospital's clinical entries.

### 3. Doctor-in-the-Loop AI Assistant (Gemini)

- **Plain-Language Summaries:** Translates complex clinical findings into accessible explanations for patients.
- **Clinician Decision Support:** Drafts analysis suggestions and recommendations for doctors to review.
- **Strict Safety Rails:** AI never diagnoses or prescribes independently. All AI outputs are strictly treated as drafts requiring explicit physician confirmation before reaching patient records.
- **De-identified Processing:** No Social Security Numbers or personally identifiable information are transmitted to external AI endpoints.

### 4. Direct Doctor-Patient Messaging

- Dedicated, secure chat threads between patients and each of their attending doctors across different clinics.
- Real-time unread badges on the physician dashboard to flag incoming patient inquiries.
- Isolated conversation threads per doctor to maintain clear medical communication boundaries.

### 5. Granular Privacy & Family Sharing

- **Confidential Mode:** One-click toggle allowing patients to completely hide records from family members when needed.
- **Category-Level Sharing:** Granular controls to toggle visibility for specific record types (e.g., sharing general checkups while keeping mental health or lab results private).
- **Access Logs & Security:** Transparent view of who accessed records and when, backed by two-step verification safeguards.

---

## 🛠 Tech Stack

- **Framework:** [TanStack Start v1](https://tanstack.com/start) (Full-stack React 19 with SSR/SSG and server functions)
- **Routing:** TanStack Router (type-safe file-based routing)
- **Styling:** Tailwind CSS v4 & semantic design tokens
- **Backend & Database:** Lovable Cloud (PostgreSQL with Row-Level Security)
- **AI Engine:** Google Gemini (streaming via SSE with server-side cancellation handling)
- **Testing:** Vitest & Playwright

---

## 🔒 Security & Medical Data Principles

- **Human-in-the-Loop:** Clinical suggestions remain uncommitted drafts until a verified clinician approves them.
- **Optimistic Concurrency & Revision Checks:** Multi-hospital updates use atomic, revision-checked writes to prevent concurrent doctors from overwriting each other's notes.
- **Row-Level Security (RLS):** Database policies enforce strict separation between medical records, doctor actions, and public demo state.
- **Fail-Safe Streaming:** Centralized SSE parsing requires complete, verified responses before applying any AI-generated drafts.

---

## 💻 Getting Started Locally

```bash
# Clone the repository
git clone <repository-url>
cd curely

# Install dependencies
npm install

# Start the development server
npm run dev
```
