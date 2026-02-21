# AI Resume Optimizer - LLM-Powered Application Generator

> **One CV. Perfect Applications.**  
> Uses LLM technology to intelligently analyze your resume and generate perfectly optimized job applications

## Credits

This project is based on 
**Original Repository:** [LLM_Writes_Job_Applications](https://github.com/bhatia2akshit/LLM_Writes_Job_Applications)

Special thanks to the open-source community and the following technologies that power this application:
- **LangChain** - LLM application framework
- **FastAPI** - Modern Python web framework
- **React + Vite** - Frontend framework
- **HuggingFace** - LLM inference API
- **Docker** - Containerization platform

---

## 🤖 What is AI Resume Optimizer?

**AI Resume Optimizer** is an intelligent resume optimization and job application generation platform powered by advanced Large Language Models (LLM). It instantly:

✨ **Analyzes Your Resume** - Extracts key skills, experience, and qualifications using LLM  
✨ **Understands Job Requirements** - Deep analysis of job descriptions to identify must-have skills  
✨ **Generates Optimized Applications** - Creates perfectly matched cover letters and responses  
✨ **Optimizes Keywords** - AI aligns your resume with job-specific keywords  
✨ **Saves Hours** - Generate professional applications in minutes, not hours  

### 🏗️ Architecture & Technology Stack

- **Frontend:** React + Vite (Modern, fast UI - port 3000 with Docker, 5173 locally)
- **Backend:** FastAPI + LangChain (Powerful AI Agent with LLM - port 8080)
- **LLM Engines:** HuggingFace 🤗, OpenAI GPT, Mistral
- **Processing:** PyPDF (Intelligent document extraction)
- **Deployment:** Docker (One-click containerized setup)

---

## 🤖 AI & LLM Intelligence Features

**Powered by Advanced Language Models for Intelligent Resume Optimization:**

### Core AI Capabilities
| Feature | Description |
|---------|-------------|
| 🧠 **Deep Semantic Understanding** | LLM analyzes skills, experience, and qualifications at semantic level |
| 📝 **Intelligent Text Generation** | AI generates natural, compelling application content optimized for jobs |
| 🎯 **Smart Keyword Extraction** | Identifies job-specific keywords and aligns resume language automatically |
| 🔄 **Context-Aware Optimization** | Rephrases your experience to match job requirements intelligently |
| 💡 **Semantic Matching** | Understands job requirements beyond simple keyword matching |
| ⚡ **Fast & Efficient** | Optimized LLM inference (5-60 seconds per application) |
| 🔐 **Privacy-Focused** | Your resume data is processed securely, not stored permanently |

### 🚀 Supported LLM Providers
- **🤗 HuggingFace** (Default, Recommended) - Free, fast inference with models like Qwen, Llama, Mistral
- **🟢 OpenAI** - Premium quality with GPT-4 & GPT-3.5 (requires paid API key)
- **🟣 Mistral** - Fast and capable models (requires API key, free tier available)

### 🔧 LLM Agent Tools
The AI agent uses specialized tools for resume optimization:
1. **extract_cv_information** - Parses and structures resume data
2. **extract_jd_keywords** - Identifies key job requirements
3. **compare_cv_data** - Matches your skills to job needs
4. **optimize_cv** - Enhances content for job relevance

---

### Option 1: Docker (Recommended - Fastest)
- **Pros:** No Node.js/Python installation needed, one command, isolated environment
- **Time:** ~25 minutes total
- **Requirements:** Docker Desktop only

### Option 2: Local Development (Advanced)
- **Pros:** Better for development, inspect code
- **Time:** ~30 minutes 
- **Requirements:** Python 3.8+, Node.js + npm

---

## 🐳 Option 1: Run with Docker

### Prerequisites
- Download and install [Docker Desktop](https://www.docker.com/products/docker-desktop)
- Ensure Docker is running (check system tray)
- Have `.env.local` file in project root with:
  ```
  HUGGINGFACEHUB_API_TOKEN=hf_your_token_here
  ```

### Get Your HuggingFace Token
1. Go to https://huggingface.co/settings/tokens
2. Create a new token or copy existing one
3. Create `.env.local` file in project root with the token above

### Run the Project (3 Steps)

```powershell
# 1. Navigate to project
cd C:\Users\vineet\IdeaProjects\LLM_Writes_Job_Applications

# 2. Start all services
docker compose up --build

# 3. Open browser
# Frontend: http://localhost:3000
# Backend: http://localhost:8080
```

**First run:** Docker downloads ~500MB images (5-10 minutes). Subsequent runs are faster.

**Logs to expect:**
```
✓ Frontend running on http://0.0.0.0:80
✓ Backend running on http://0.0.0.0:8080
```

### Stop the Services
```powershell
# Press Ctrl+C in terminal, or run:
docker compose down
```

### Common Docker Commands
```powershell
docker compose up --build      # Start fresh
docker compose up              # Start (reuse images)
docker compose down            # Stop and remove
docker compose down -v         # Stop and remove volumes
docker compose logs            # View logs
docker compose ps              # Show running containers
```

### Docker Troubleshooting

| Issue | Solution |
|-------|----------|
| "docker: command not found" | Install Docker Desktop |
| "daemon not running" | Start Docker Desktop app |
| Port 3000 already in use | Change in docker-compose.yml: `"3001:80"` |
| Port 8080 already in use | Change in docker-compose.yml: `"8081:8080"` |
| Token not loaded | Restart: `docker compose down` → `docker compose up --build` |

---

## 💻 Option 2: Local Setup (Without Docker)

### Prerequisites
- Python 3.8+ (check: `python --version`)
- Node.js + npm (check: `node --version` and `npm --version`)
- `.env.local` file with HuggingFace token (same as Docker)

### Step 1: Install Node.js (if not installed)

**Error:** "npm: command not found"? → Node.js is missing

1. Download from https://nodejs.org/
2. Click **LTS** button (green, left side)
3. Run the installer - accept all defaults
4. **IMPORTANT:** Check "Add Node.js to PATH"
5. **Restart PowerShell completely** (close all windows)
6. Open new PowerShell and verify:
   ```powershell
   node --version    # Should show v20.X.X
   npm --version     # Should show 10.X.X
   ```

### Step 2: Backend Setup (Terminal 1)

```powershell
cd C:\Users\vineet\IdeaProjects\LLM_Writes_Job_Applications\backend

# Create virtual environment (one-time)
python -m venv .venv

# Activate virtual environment
.\.venv\Scripts\Activate.ps1

# Install Python packages (~2 minutes)
python -m pip install -U pip
python -m pip install -r requirements.txt

# Start backend server
uvicorn app:app --host 0.0.0.0 --port 8080 --reload
```

**Success indicator:**
```
INFO:     Uvicorn running on http://0.0.0.0:8080
```

✅ **Keep this terminal open!**

### Step 3: Frontend Setup (Terminal 2 - NEW Window)

Open a **NEW PowerShell** window:

```powershell
cd C:\Users\vineet\IdeaProjects\LLM_Writes_Job_Applications\frontend

# Install npm dependencies (~3 minutes first time)
npm install

# Start development server
npm run dev
```

**Success indicator:**
```
VITE v5.X.X dev server running at:
➜  Local:   http://localhost:5173/
```

✅ **Keep this terminal open!**

### Step 4: Access the Application

Open your browser and go to:
- **Frontend:** http://localhost:5173 (Vite dev server)
- **Backend API:** http://localhost:8080 (FastAPI)

### Stop the Services

In each terminal window:
```powershell
# Press Ctrl+C to stop
```

---

## 📁 Project Structure

### Frontend (`frontend/`)
```
frontend/
├── package.json           # npm dependencies
├── vite.config.js         # Vite configuration
├── index.html             # HTML entry
├── nginx.conf             # Nginx config (Docker)
└── src/
    ├── main.jsx           # App entry point
    ├── App.jsx            # Main UI component
    │   ├─ Resume file upload
    │   ├─ Job description input
    │   └─ Results display
    └── index.css          # Styling
```

### Backend (`backend/`)
```
backend/
├── requirements.txt       # Python dependencies
├── app.py                 # FastAPI server
├── agent.py               # LangChain agent logic
├── llm_service.py         # LLM provider management
├── prompt_service.py      # Prompt templates
├── prompt.yaml            # Prompt configurations
├── tools.py               # LLM agent tools
├── helper.py              # Utility functions
└── env_loader.py          # Environment loader
```

---

## 🔄 AI Resume Optimizer - Intelligent Processing Flow

### User Interaction
1. Open http://localhost:3000 (or 5173 locally)
2. Upload your resume (PDF file)
3. Paste job description text
4. Click "Generate Optimized Application" ✨

### 🧠 LLM-Powered Resume Optimization

The LangChain agent powered by Large Language Models performs intelligent analysis:

1. **🔍 Smart PDF Processing** - Extracts structured data from your resume using intelligent text extraction
2. **📊 Job Description Analysis** - LLM parses job posting to understand requirements at semantic level
3. **🎯 Skills Extraction** - AI identifies key skills from both resume and job description
4. **⚡ Intelligent Matching** - LLM compares your experience against job requirements intelligently
5. **🔤 Keyword Optimization** - AI aligns your resume language with job-specific keywords
6. **✍️ Content Generation** - LLM generates natural, compelling optimized application text
7. **📝 Professional Formatting** - Returns beautifully formatted, ready-to-send application

### 📥 What Goes In
- **Resume Document:** PDF file (your resume)
- **Job Description:** Text (role requirements & keywords)
- **API Token:** `.env.local` (HuggingFace/OpenAI authentication for LLM access)

### 📤 What Comes Out
- **AI-Optimized Application:** Perfectly optimized cover letter/response
- **Keyword-Optimized Content:** Your experience rephrased to match job requirements
- **Professional Format:** Ready-to-use application text

---

## 🔧 Environment Variables

Create `.env.local` in project root:

```
# Required: HuggingFace API Token
HUGGINGFACEHUB_API_TOKEN=hf_your_token_here

# Optional: Other LLM providers
OPENAI_API_KEY=sk_your_key_here
MISTRAL_API_KEY=your_key_here
```

**Get HuggingFace Token:**
1. Visit https://huggingface.co/settings/tokens
2. Create new token (or use existing)
3. Copy the token value
4. Paste in `.env.local`

---

## 🆘 Troubleshooting

### Common Issues

**"npm: command not found"**
- Solution: Install Node.js from https://nodejs.org/
- After install: Restart PowerShell completely
- Verify: `npm --version`

**"Port 3000/5173/8080 already in use"**
- Docker: Edit `docker-compose.yml` ports section
- Local: Kill the process or change the port

**"API token not working"**
- Verify token in `.env.local`
- Ensure token is valid: https://huggingface.co/settings/tokens
- Restart backend service

**"PDF upload fails"**
- Ensure PDF is not corrupted
- File size < 10MB recommended
- Try with different PDF

**"Backend takes too long / times out"**
- First call is slow (model loading)
- Subsequent calls are faster
- Check `.env.local` token is correct

### Getting Help

Check these files for more detailed information:
- `DOCKER_SETUP.md` - Detailed Docker explanation
- `PROJECT_GUIDE.md` - Architecture deep dive
- `EVERYTHING_EXPLAINED.md` - How everything works

---

## ✅ Verification Checklist

- [ ] `.env.local` file created with HuggingFace token
- [ ] (Docker) Docker Desktop installed and running
- [ ] (Local) Node.js installed (`npm --version` works)
- [ ] (Local) Python 3.8+ installed (`python --version` works)
- [ ] Backend running (http://localhost:8080 accessible)
- [ ] Frontend running (http://localhost:3000 or 5173 accessible)
- [ ] Can upload PDF file
- [ ] Can enter job description
- [ ] Can click "Generate Application"
- [ ] Receives application output

---

## 📊 Performance Notes

- **First backend call:** ~30-60 seconds (model loading from HuggingFace)
- **Subsequent calls:** ~5-15 seconds (model cached)
- **Docker first run:** 5-10 minutes (image download)
- **Docker restart:** 10-20 seconds (containers start)

---

## 🎯 Next Steps

1. Choose Docker or Local setup above
2. Follow the 3-4 step setup
3. Open http://localhost:3000 (Docker) or http://localhost:5173 (Local)
4. Upload your resume and job description
5. Generate your optimized application!

**That's it!** AI Resume Optimizer is fully functional after these setup steps.

