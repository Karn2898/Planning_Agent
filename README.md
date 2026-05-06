# 📋 Planning Agent

**AI-Powered Blog Planning & Content Strategy System**

Turn your content ideas into structured, actionable blog plans with intelligent task generation powered by LLMs and LangGraph.
<img width="1366" height="693" alt="Annotation 2026-05-06 221419" src="https://github.com/user-attachments/assets/f70078fc-3279-4a7a-9f7c-a14f542d3326" />



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

---

**Made with ❤️ by the Planning Agent Team**
