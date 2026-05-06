# 📋 Planning Agent

**AI-Powered Blog Planning & Content Strategy System**

Turn your content ideas into structured, actionable blog plans with intelligent task generation powered by LLMs and LangGraph.

---

## 🎯 What is Planning Agent?

Planning Agent is a sophisticated multi-stage system that transforms high-level content briefs into detailed, step-by-step blog planning strategies. Using advanced language models and graph-based workflows, it intelligently breaks down complex writing projects into manageable tasks with research requirements, citation needs, and code examples.

Perfect for:
- **Content Strategists** creating structured editorial calendars
- **Technical Writers** planning comprehensive documentation
- **Bloggers** seeking data-driven content structure
- **Dev Teams** automating content planning workflows

---

## ✨ Key Features

- **🤖 Multi-Stage Planning Pipeline** – Three-stage workflow for comprehensive content planning
- **📊 Smart Task Generation** – Automatically creates 3-6 structured tasks per plan
- **🎓 Context-Aware** – Understands audience, tone, and content type
- **🔍 Metadata-Rich** – Tags, research requirements, and citation tracking built-in
- **⚡ LangGraph Integration** – State-machine based workflows for reliability
- **🌐 LLM-Powered** – OpenAI integration with extensible model support
- **💾 Type-Safe** – Pydantic schemas for schema validation

---

## 🏗️ Architecture

```
┌─────────────────────────┐
│   User Brief/Topic      │
└────────┬────────────────┘
         │
    ┌────▼────────────────────┐
    │   Stage 1: Planning      │
    │   - Understand goal      │
    │   - Define audience      │
    └────┬────────────────────┘
         │
    ┌────▼────────────────────┐
    │   Stage 2: Task Gen      │
    │   - Create subtasks      │
    │   - Set requirements     │
    └────┬────────────────────┘
         │
    ┌────▼────────────────────┐
    │   Stage 3: Refinement    │
    │   - Optimize tasks       │
    │   - Add metadata         │
    └────┬────────────────────┘
         │
    ┌────▼────────────────────┐
    │   Structured Blog Plan   │
    │   (Title, Tasks, Goals)  │
    └─────────────────────────┘
```

---

## 🚀 Quick Start

### Prerequisites
- Python 3.12+
- OpenAI API key

### Installation

```bash
# Clone the repository
git clone https://github.com/Karn2898/Planning_Agent.git
cd Planning_Agent

# Create virtual environment
python -m venv agent
source agent/bin/activate  # On Windows: agent\Scripts\activate

# Install dependencies
pip install -r Requirements.txt
```

### Configuration

Create a `.env` file in the root directory:
```env
OPENAI_API_KEY=your_api_key_here
```

### Usage

**Backend (LangGraph Workflow):**
```python
from bwa_backend import Plan, Task

# Define your content plan
plan = Plan(
    blog_title="Understanding Transformers",
    audience="Technical readers",
    tone="Educational",
    blog_kind="explainer",
    constraints=["Keep under 2000 words", "Include code examples"]
)

# Run the planning workflow
# ...execution happens across stages 1-3
```

**Frontend (Streamlit):**
```bash
streamlit run frontend.py
```

---

## 📂 Project Structure

```
Planning_Agent/
├── bwa_backend.py              # Core planning engine using LangGraph
├── frontend.py                 # Streamlit web interface
├── stage_1.ipynb               # Initial planning stage
├── stage_2.ipynb               # Task generation stage
├── stage_3.ipynb               # Refinement stage
├── Requirements.txt            # Python dependencies
└── README.md                   # This file
```

---

## 🔧 Tech Stack

- **[LangGraph](https://langchain-ai.github.io/langgraph/)** – State machine workflows
- **[LangChain](https://www.langchain.com/)** – LLM orchestration
- **[Pydantic](https://docs.pydantic.dev/)** – Data validation
- **[OpenAI API](https://openai.com/api/)** – Language model backend
- **[Streamlit](https://streamlit.io/)** – Web interface
- **[Pandas](https://pandas.pydata.org/)** – Data handling

---

## 📊 Core Data Models

### Plan Schema
```python
Plan(
    blog_title: str
    audience: str
    tone: str
    blog_kind: "explainer" | "tutorial" | "news_roundup" | "comparison" | "system_design"
    constraints: List[str]
    tasks: List[Task]
)
```

### Task Schema
```python
Task(
    id: int
    title: str
    goal: str                    # One-sentence objective
    bullets: List[str]           # 3-6 action items
    target_words: int            # 120-550 words
    tags: List[str]
    requires_research: bool
    requires_citations: bool
    requires_code: bool
)
```

---

## 🎓 Example Workflow

```python
# Input: High-level content idea
brief = "Create a guide about self-attention in transformers"

# Process through 3 stages...

# Output: Structured plan
{
  "blog_title": "Unlocking Self-Attention in Transformers",
  "audience": "ML engineers and researchers",
  "tone": "Technical but accessible",
  "tasks": [
    {
      "id": 1,
      "title": "Attention Mechanism Basics",
      "goal": "Explain how attention weights work",
      "bullets": ["Query-key-value framework", "Softmax normalization", "Output computation"],
      "requires_research": True,
      "requires_citations": True
    },
    # ... more tasks
  ]
}
```

---

## 🛣️ Roadmap

- [ ] Multi-LLM support (Claude, Gemini, local models)
- [ ] Custom prompt templates
- [ ] Team collaboration features
- [ ] Export to Notion/Google Docs
- [ ] Content performance analytics
- [ ] Automated content calendar scheduling

---

## 🤝 Contributing

Contributions are welcome! Please:
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

---

## 📝 License

This project is licensed under the MIT License – see the [LICENSE](LICENSE) file for details.

---

## 💡 Tips for Best Results

- **Be specific** with audience and tone definitions
- **Set realistic constraints** that align with your platform
- **Review generated tasks** and adjust as needed
- **Use citations** for research-heavy content
- **Include code** for technical tutorials and system design posts

---

## 📧 Support

Have questions or found a bug? 
- Open an [issue](https://github.com/Karn2898/Planning_Agent/issues)
- Check existing documentation in the notebooks

---

**Made with ❤️ by the Planning Agent Team**