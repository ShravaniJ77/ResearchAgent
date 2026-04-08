# ScholAR - Autonomous Research Agent

An autonomous research agent that searches, analyzes, and synthesizes academic literature with minimal human intervention.

## 🎯 Key Features

### Autonomy & Intelligence

- **🤖 Iterative Deep-Dive Search**: Autonomously detects sub-topics and searches recursively
- **📊 Saturation Detection**: Knows when to stop searching (diminishing returns)
- **🤔 The Skeptic Agent**: Plays devil's advocate to identify blind spots
- **🔍 Thought Transparency**: Full agent decision log visible to users

### Research Capabilities

- **🕸️ Interactive Knowledge Graph**: Living network of papers and citations
- **🤝 Contradiction Matrix**: Identifies disagreements and debates in literature
- **🎯 Research Gap Analysis**: Reveals opportunities for future work
- **📈 Trend Analysis**: Tracks methodology evolution over time
- **💡 Grant Proposal Generator**: Suggests concrete next research steps

### Smart Optimization

- Routes simple tasks to fast/free LLMs
- Routes complex reasoning to smarter models
- Batch processing for efficiency
- Concept extraction and similarity checking

## 📁 Project Structure

```
scholarpython/
├── src/                    # Core application code
│   ├── agent.py           # Autonomous research agent
│   ├── config.py          # Configuration & API keys
│   ├── models.py          # Data structures
│   ├── semantic_scholar.py # Semantic Scholar API client
│   ├── llm_client.py      # OpenRouter LLM client
│   ├── pdf_generator.py   # PDF/HTML/MD report generation
│   └── mock_data.py       # Demo data fallback
│
├── app/                    # UI Application
│   └── streamlit_app.py   # Main Streamlit interface
│
├── scripts/               # Utility scripts
│   ├── verify.py         # System verification
│   ├── test_agent.py     # Agent tests
│   ├── run.sh            # Linux/Mac launcher
│   └── run.bat           # Windows launcher
│
├── docs/                  # Documentation
│   ├── START_HERE.md     # Quick start guide
│   ├── SETUP.txt         # Setup instructions
│   ├── QUICKSTART.txt    # Quick reference
│   ├── UPDATES.md        # Recent changes
│   └── PROJECT_SUMMARY.txt # Full project overview
│
├── tests/                 # Test files
│   └── test_agent.py     # Agent tests
│
├── requirements.txt       # Python dependencies
├── .gitignore            # Git ignore rules
└── README.md             # This file
```

## 🚀 Quick Start

### 1. Clone & Install

```bash
git clone https://github.com/yourusername/scholarpython.git
cd scholarpython
pip install -r requirements.txt
```

### 2. Verify Installation

```bash
python scripts/verify.py
```

### 3. Run the Application

```bash
# Windows
scripts/run.bat

# Linux/Mac
bash scripts/run.sh

# Or directly
streamlit run app/streamlit_app.py
```

Then open: `http://localhost:8501`

### 4. Try a Research Topic

Example: "Transformer Models"

## 💡 How It Works

### Phase 1: Iterative Search

1. Start with user query
2. Search Semantic Scholar
3. Extract concepts from results
4. Calculate saturation score
5. If low saturation, autonomously identify sub-topic
6. **Recursive search** on the sub-topic (up to 3 levels deep)
7. Stop when saturation reaches 85%

### Phase 2: Paper Enhancement

1. Extract methodology from each abstract
2. Extract main conclusions
3. Extract key concepts
4. Build concept map

### Phase 3: Analysis & Insight

1. **Contradiction Detection**: Use LLM to find conflicting claims
2. **Gap Analysis**: Identify what's missing
3. **Clustering**: Group papers by methodology
4. **Trend Analysis**: Methodology evolution by year

### Phase 4: Report Generation

1. Generate comprehensive markdown report
2. Create visualization dashboards
3. Generate grant proposal based on gaps
4. Provide "Devil's Advocate" critical review

## 📊 Technology Stack

| Component           | Technology               |
| ------------------- | ------------------------ |
| **Search Engine**   | Semantic Scholar API     |
| **LLM Provider**    | OpenRouter (free tier)   |
| **Frontend**        | Streamlit                |
| **Visualization**   | Plotly, Streamlit-Agraph |
| **Data Processing** | Pandas, NetworkX         |

## 🔑 Configuration

Edit `config.py` to adjust:

- `MAX_PAPERS_PER_SEARCH`: Results per API call (default: 20)
- `RECURSIVE_SEARCH_MAX_DEPTH`: Max search iterations (default: 3)
- `SATURATION_THRESHOLD`: When to stop (default: 85%)
- `BATCH_SIZE`: Papers per enhancement batch (default: 5)

## 🎓 API Keys Required

The system uses two FREE APIs:

### Semantic Scholar

Get key: https://www.semanticscholar.org/product/api
Add to `config.py`:

```python
SEMANTIC_SCHOLAR_API_KEY = "your_key_here"
```

### OpenRouter (Free Models)

Get key: https://openrouter.ai
Add to `config.py`:

```python
OPENROUTER_API_KEY = "your_key_here"
```

**Note**: Uses only free tier models!

## 🏆 Winning Features

### 1. Autonomy

- ✅ Decides what to search autonomously
- ✅ Decides when to stop (saturation detection)
- ✅ Decides next search direction (recursive deep-dive)

### 2. Transparency

- ✅ Full "Thought Log" showing agent decisions
- ✅ Real-time status updates
- ✅ Explanation of methodology choices

### 3. Intelligence

- ✅ Finds contradictions (not just summaries)
- ✅ Identifies research gaps (not just conclusions)
- ✅ Generates grant proposals (actionable insights)
- ✅ Devil's advocate review (critical analysis)

### 4. User Experience

- ✅ Clean Streamlit interface
- ✅ Interactive knowledge graph
- ✅ Downloadable reports
- ✅ Dashboard with metrics

## 📝 Example Usage

1. **Input**: "Federated Learning in Healthcare"
2. **Agent thinks**:
   - "Searching 'Federated Learning in Healthcare'..."
   - "Found 15 papers. Extracting concepts: differential privacy, edge computing, communication efficiency..."
   - "Noticed 'differential privacy' in 12/15 papers. Starting secondary search..."
   - "Results show diminishing novelty. Moving to analysis phase..."
3. **Output**:
   - 23 papers analyzed
   - 4 contradictions identified (e.g., "Paper A: DP necessary" vs "Paper B: DP overhead too high")
   - 5 research gaps discovered
   - Grant proposal: "Investigate post-quantum privacy in federated settings"

## 🐛 Troubleshooting

### "API Error: 403"

- Check API keys in `config.py`
- Ensure quota limits not exceeded
- Verify network connectivity

### "LLM Request Timed Out"

- OpenRouter may be slow, retry
- Use faster model for testing
- Check `LLM_TIMEOUT` in config.py

### "Import Error"

- Run `pip install -r requirements.txt`
- Check Python version (3.8+)
- Run `validate.py` to diagnose

## 📚 References

- [Semantic Scholar API](https://www.semanticscholar.org/product/api)
- [OpenRouter](https://openrouter.ai)
- [Streamlit Docs](https://docs.streamlit.io)
- [NetworkX](https://networkx.org)

## 🎉 Credits

**ScholAR** - Built for the Hackathon
Demonstrating autonomous AI research capability.

---

**Questions?** Check the code comments or run `validate.py` for system diagnostics.
"# SXAG039" 
