# CareerForge AI - AI-Powered Career Acceleration System

**Track:** Agents for Good (Education)

An intelligent multi-agent system that helps job seekers navigate every stage of their career journey—from resume optimization to salary negotiation.

---

## 🎯 Problem Statement

Job searching is overwhelming and time-consuming. Candidates struggle with:
- Creating ATS-friendly resumes that pass automated screening
- Finding relevant job opportunities in a sea of listings
- Preparing for company-specific interviews
- Negotiating fair compensation, especially during career transitions

Traditional job search tools are fragmented, you need multiple platforms and services, each handling only one piece of the puzzle.

---

## 💡 Solution

CareerForge AI is a comprehensive multi-agent system that acts as your personal career coach, handling five critical areas:

1. **Resume Tailor Agent** - Optimizes resumes for specific job descriptions without fabricating experience
2. **ATS Scorer Agent** - Analyzes resume compatibility with applicant tracking systems
3. **Job Scraper Agent** - Finds and ranks recent job postings based on your profile
4. **Interview Intelligence Agent** - Generates company-specific interview prep materials
5. **Salary Negotiation Agent** - Provides data-driven compensation strategies with career transition support

---

## 🏗️ Architecture

### Multi-Agent System Design

```
User Input (Resume + Job Description)
    ↓
┌─────────────────────────────────────────┐
│   CareerForge Orchestrator              │
└─────────────────────────────────────────┘
    ↓
┌───────────────┐  ┌───────────────┐  ┌───────────────┐
│ Resume Tailor │→ │  ATS Scorer   │→ │ Job Scraper   │
└───────────────┘  └───────────────┘  └───────────────┘
                           ↓
            ┌──────────────┴──────────────┐
            ↓                             ↓
   ┌─────────────────┐         ┌──────────────────┐
   │   Interview     │         │     Salary       │
   │  Intelligence   │         │   Negotiation    │
   └─────────────────┘         └──────────────────┘
```

### Key Features Implemented

✅ **Multi-Agent System** - Five specialized agents working sequentially  
✅ **Custom Tools** - Resume parsing, ATS scoring, job scraping, salary analysis  
✅ **External APIs** - SerpAPI for job search, web scraping for market data  
✅ **Session Management** - InMemorySessionService for conversation state  
✅ **Context Engineering** - Structured prompts to prevent hallucination

---

## 🚀 Demo

The system processes a sample resume and job description through all five agents:

**Input:**
- Resume: ML Engineer with 2 years experience
- Target: AI Engineer position at Capgemini Engineering

**Output:**
- 5 tailored job matches with scoring
- Optimized resume suggestions
- 10 interview questions with STAR-format answers
- Salary negotiation strategy
---

## 🛠️ Technical Stack

- **Framework:** Google ADK (Agent Development Kit)
- **LLM:** Gemini 2.0 Flash (gemini-2.0-flash-exp)
- **APIs:** SerpAPI (job search), Levels.fyi (salary data)
- **Tools:** Custom Python functions for parsing and analysis
- **Memory:** InMemorySessionService, InMemoryMemoryService

---

## 📦 Setup Instructions

### Prerequisites
- Python 3.8+
- Google API Key (for Gemini)
- SerpAPI Key (for job search)

### Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/careerforge-ai.git
cd careerforge-ai

# Install dependencies
pip install google-genai google-adk serpapi beautifulsoup4 requests

# Set environment variables
export GOOGLE_API_KEY="your_google_api_key"
export SERPAPI_API_KEY="your_serpapi_key"
```

### Run the Demo

Open the notebook `careerforge_ai_agent_system.ipynb` in Google Colab or Jupyter:

```bash
jupyter notebook careerforge_ai_agent_system.ipynb
```

Run all cells to see the complete workflow in action.

---

## 🎓 What I Learned

Building this project taught me:
- How to design **sequential multi-agent workflows** with clear handoffs
- The importance of **preventing LLM hallucination** through strict tool constraints
- Real-world challenges of **web scraping** and API rate limiting
- Balancing **deterministic tools** (parsing, scoring) with **LLM reasoning**

The biggest challenge was preventing the Resume Tailor Agent from inventing work experience. I solved this by:
1. Explicitly instructing the agent to mark suggestions with `[SUGGESTED]`
2. Using tool outputs (parsed resume data) as ground truth
3. Requiring the agent to preserve original employment history verbatim

---

## 🌟 Why This Matters

Job searching is stressful, especially for career switchers. CareerForge AI democratizes access to career coaching by:
- Making professional resume optimization available to everyone
- Providing real-time job market intelligence
- Helping candidates negotiate fair compensation based on data
- Reducing the time and anxiety of interview preparation

**Impact:** This tool can save job seekers 10-15 hours per week and increase their chances of landing interviews by optimizing for ATS systems.

---

## 🙏 Acknowledgments

Built as part of the Kaggle 5-Day AI Agents Intensive Course (November 2025).

Special thanks to the Google ADK team for the powerful agent framework!
