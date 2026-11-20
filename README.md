
# Meeting Notes to Action Items Using Structured LLM Outputs

## Team Details

**Course:** Generative AI and AI Platform Engineering (25CS2207E)  
**Academic Year:** 2026–27, Term-II  
**Section:** 7  
**Team Number:** 9  

### Team Members

| Roll Number | Student Name |
|---|---|
| 2520030258 | Sai Saranya |
| 2520030436 | Eesha Yuktha |
| 2520030551 | M. Bhavitha |

**Project Supervisor:** Dr. K. Anusha

---

## Abstract

Meeting discussions often end without a clear, verifiable record of who must do what and by when. This project aims to develop a web application that converts unstructured meeting transcripts, entered as text or uploaded as documents, into structured action items using a Large Language Model (LLM).

The system identifies tasks, responsible individuals, deadlines and priorities, and generates structured JSON outputs containing supporting evidence quotes from the original transcript. A governed prompt and validation mechanism ensures that missing information is represented as null and unsupported information is flagged or refused rather than invented.

The application includes transcript tokenisation, token budgeting, schema validation, an egress gate and a review dashboard that allows users to inspect, correct and export approved action items as CSV, JSON and PDF.

The system will be evaluated using annotated meeting transcripts against a rule-based baseline, with extraction quality, safety, processing cost and response latency measured.

The expected outcome is a reliable and auditable application that reduces manual meeting follow-up effort while maintaining human control over the final action items.

---

## Problem Identification

Meetings generate large amounts of unstructured information containing discussions, decisions and commitments. Identifying action items, responsible individuals and deadlines manually is time-consuming and inconsistent.

Important tasks may be overlooked, responsibilities may be assigned incorrectly, and follow-up activities may be delayed. The project addresses these challenges by using Generative AI to extract and organise actionable information from meeting transcripts.

## Proposed Solution

The proposed application converts meeting transcripts into structured and verifiable action items.

Key functionalities include:

- Accepting meeting notes through text input or document uploads.
- Extracting tasks, decisions, owners, deadlines and priorities using an LLM.
- Generating structured JSON outputs.
- Validating outputs against a predefined schema.
- Verifying supporting evidence against the original transcript.
- Handling missing information without inventing details.
- Allowing users to review, edit and reject generated action items.
- Exporting approved results as CSV, JSON and PDF.

## Generative AI Concepts Used

| Concept | Application |
|---|---|
| LLM-based Information Extraction (CO1) | Extracts action items from unstructured meeting transcripts. |
| Typed Model Boundary and Schema Validation (CO1) | Ensures generated responses follow a predefined JSON structure. |
| Prompt Governance and Trust Hierarchy (CO3) | Prevents instructions inside meeting transcripts from being treated as system instructions. |
| Evidence Grounding and Refusal (CO3) | Requires supporting transcript quotes and flags unsupported information. |
| Tokenisation and Token Budgeting (CO2) | Processes long transcripts within the model's token limits. |
| Egress Gate and Resilience (CO3) | Validates responses and handles failures safely. |
| Evaluation and Safety Floor (CO4) | Evaluates extraction quality and prevents fabricated owners or deadlines. |
| Cost and Latency Budgeting with Caching (CO5) | Measures processing cost and response time while reducing repeated API calls. |

## Technologies, Models, APIs and Frameworks

| Technology | Purpose |
|---|---|
| Python | Main programming language |
| Hosted LLM API | Generates structured action items |
| Pydantic / JSON Schema | Structured output validation |
| Streamlit | User interface and review dashboard |
| python-docx | DOCX document processing |
| PDF text-extraction library | PDF transcript processing |
| SQLite | Stores execution traces and cached results |
| Pandas | Data handling and CSV exports |
| ReportLab | PDF report generation |
| Git and GitHub | Version control and collaboration |

## Setup and Execution Instructions

### Prerequisites

- Python 3.10 or later
- pip
- Git
- Visual Studio Code
- API key for the selected hosted LLM provider

### 1. Clone the Repository

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
cd <PROJECT_FOLDER_NAME>
```

### 2. Create a Virtual Environment

```bash
python -m venv venv
```

Activate the environment.

**Windows:**
```bash
venv\Scripts\activate
```

**macOS / Linux:**
```bash
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure Environment Variables

Create a `.env` file in the project root directory.

Add your API key:

```env
LLM_API_KEY=your_api_key_here
```

Do not commit your `.env` file or expose your API key on GitHub.

### 5. Run the Application

```bash
streamlit run app.py
```

Open the local URL displayed in the terminal to access the application.

**Note:** The commands, dependency list and environment variable names should be updated to match the final implementation.

---

## Proposed Implementation Workflow

1. Meeting transcript input through text or document upload.
2. Text extraction and tokenisation.
3. Transcript segmentation based on the token budget.
4. LLM processing using governed prompts.
5. Structured JSON generation.
6. Schema validation and evidence verification.
7. Egress gate checks and refusal of unsupported information.
8. Human review through the dashboard.
9. Export of approved action items.
10. Testing and evaluation against a rule-based baseline.

## Course Outcome Alignment

| Course Outcome | Implementation |
|---|---|
| CO1 | Governed AI product seam, typed model boundary, evidence, refusal and trace. |
| CO2 | Tokenisation and token budgeting. |
| CO3 | Prompt governance, trust hierarchy, egress gate, resilience and evidence grounding. |
| CO4 | Evaluation sets, rule-based baseline, annotator agreement and safety floor. |
| CO5 | Cost and latency measurement with response caching. |

## Expected Outcome

The project aims to deliver a functional web application that converts unstructured meeting transcripts into structured, evidence-supported action items.

The application will provide an organised review dashboard, validated JSON outputs, safe handling of missing information and export functionality.

It aims to reduce manual meeting follow-up effort while maintaining reliability, accountability, transparency and human control over generated results.

---

## Current Project Phase Status

**Status:** Project Planning and Design / Initial Development

The project is currently in the planning and design stage. The proposed system architecture, technology stack, implementation methodology and evaluation strategy have been defined.

Upcoming activities include:

- Development environment setup.
- Hosted LLM API integration.
- Transcript processing and tokenisation.
- Structured JSON generation and validation.
- Prompt governance and evidence verification.
- Dashboard development.
- Export functionality.
- Testing and evaluation.

*This section will be updated as the project progresses.*

---

## Team

Developed by:

- Sai Saranya
- Eesha Yuktha
- M. Bhavitha

**Course:** Generative AI and AI Platform Engineering (25CS2207E)
