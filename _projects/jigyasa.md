---
name: jigyasa
title: "Jigyasa: Agentic Interface for AlphaFold"
brief_description: "Building a production-grade Agentic Interface for the AlphaFold ecosystem that enables AI to autonomously navigate protein databases and accelerate scientific discovery"
status: Active
affiliation: "GAIR Lab × Skillplot @ BITS Pilani"
disciplines:
  - "Bioinformatics / Computational Biology"
  - "AI & Machine Learning (Bio-AI focus)"
  - "Software Engineering / Scientific Computing"
---

## Project Overview

The bioinformatics industry is **rapidly moving toward "Autonomous Science,"** yet a critical gap remains: **current AI models are "brains in a jar"**—intelligent, but disconnected from real-world scientific data.

**Project Jigyasa** addresses this industry-wide challenge by building a **production-grade "Agentic Interface"** for the AlphaFold ecosystem. You will **move beyond standard chatbots** to engineer a high-impact **Research Tool**.

By implementing advanced **"Tool Use" protocols**, you will empower an AI to:
- Actively navigate complex protein databases (UniProt, AlphaFold DB)
- Validate findings against experimental data
- Suggest next-steps in drug discovery pipelines
- Autonomously answer multi-step biological questions

This project **simulates the cutting-edge R&D workflows** currently being adopted by top AI-for-Science labs (DeepMind, MIT-IBM Watson AI Lab, Recursion Pharmaceuticals).

## Expected Outcomes

### "Bio-Agent" Python Package
A **modular Python library** allowing any LLM to query biological databases, usable for future research pipelines.

**Features:**
- UniProt API wrapper
- AlphaFold DB integration
- PDB file parser
- Query engine for complex biological questions

### Streamlit Web Application
A **functional demo** where a user can:
- Ask questions about proteins: *"What is the 3D structure of ACE2? How confident is the prediction?"*
- Get summarized answers with:
  - Structure visualization
  - pLDDT confidence scores
  - Related variants and mutations
  - Download links for PDB files

### Technical Report
**"Building Agentic Workflows for Scientific Data"**—a guide on moving from static search to autonomous discovery.

## Key Engineering Modules

### 1. The Tool Layer (The Infrastructure)

Create a **robust Python library** with comprehensive error handling:

```python
class ProteinToolkit:
    def fetch_uniprot(self, gene_name):
        """Retrieve gene metadata, sequences, variants"""
        
    def fetch_alphafold(self, protein_id):
        """Get 3D structure, confidence (pLDDT) scores"""
        
    def fetch_variants(self, protein_id):
        """Find disease-associated mutations"""
        
    def parse_pdb(self, pdb_file):
        """Extract structure metrics"""
```

**Challenge:** Design these tools with **Production Reliability**:
- Handle API rate limits gracefully
- Manage missing data (some proteins lack experimental structures)
- Cache results to minimize API calls
- Retry logic for transient failures
- Comprehensive error messages for the LLM

### 2. The Reasoning Engine (The Logic)

Use an **orchestration framework** (LangChain or LlamaIndex) to implement a **ReAct (Reason + Act) workflow:**

**Example Multi-Step Query:**
```
User: "Is SARS-CoV-2 Spike protein suitable for drug targeting?"

Agent Reasoning:
  Step 1: Retrieve Spike protein structure from AlphaFold DB
  Step 2: Check pLDDT score (confidence)
  Step 3: Identify binding pockets using BioPython
  Step 4: Search for known drugs targeting this protein
  Step 5: Assess druggability score
  Step 6: Generate summary with actionable insights
```

The agent **decides autonomously** which tools to use and in what sequence.

### 3. Automated Analysis Module (The Processor)

Integrate **BioPython** to programmatically analyze protein structures:

```python
from Bio.PDB import PDBParser, PLDDT

def analyze_structure(pdb_file):
    parser = PDBParser(QUIET=True)
    structure = parser.get_structure('protein', pdb_file)
    
    # Extract pLDDT confidence scores
    plddt_scores = extract_plddt(structure)
    
    # Classify quality
    if mean_plddt > 80:
        quality = "High Quality"
    elif mean_plddt > 50:
        quality = "Moderate (suitable for docking)"
    else:
        quality = "Disordered (unreliable)"
    
    return {
        'mean_plddt': mean_plddt,
        'quality': quality,
        'recommendations': suggest_next_steps(quality)
    }
```

**Key Metrics:**
- **pLDDT Score:** AlphaFold's confidence (0-100)
  - 90+: High confidence
  - 70-90: Confident
  - 50-70: Low confidence
  - <50: Very unreliable

## 4. Interactive Dashboard (The Interface)

Build a **Streamlit application** where researchers can:
- **Ask biological questions** in natural language
- **See the agent's reasoning** in real-time
  - "Retrieving Spike protein from AlphaFold DB..."
  - "Analyzing pLDDT confidence..."
  - "Finding drugable pockets..."
- **Visualize structures** using Py3Dmol
- **Download evidence** (PDB files, analysis reports)

**Example Interactions:**
```
Q: "Compare the drug-targetability of WT vs. Delta variant Spike protein"
Agent Output:
  [Fetching WT Spike... ✓]
  [Fetching Delta variant... ✓]
  [Analyzing structures... ✓]
  
  WT Spike:
    - pLDDT: 91.2 (High confidence)
    - Druggable pockets: 3
    - Known drugs: 5 (monoclonal antibodies)
  
  Delta Spike:
    - pLDDT: 88.7 (Confident)
    - Druggable pockets: 2
    - Difference: Reduced antibody binding
  
  Recommendation: WT remains optimal target; Delta shows resistance.

Q: "What are the consequences of the D614G mutation in Spike?"
Agent Output:
  [Searching UniProt... ✓]
  [Fetching structures... ✓]
  
  D614G Mutation:
    - Classification: Substitution
    - Impact: Moderate (affects furin cleavage)
    - Associated variants: Alpha, Delta, Omicron
    - Literature: 47 peer-reviewed papers
  
  Conclusion: This is a key driver of transmissibility.
```

## Technical Architecture

```
User Query (Natural Language)
        ↓
LLM Reasoning (ReAct Pattern)
        ↓
Tool Selection & Execution
  ├─ UniProt API
  ├─ AlphaFold DB API
  ├─ PDB Parser (BioPython)
  └─ Dosage Calculator
        ↓
Structure Analysis (pLDDT, pockets, variants)
        ↓
Answer Generation + Confidence Scores
        ↓
Streamlit UI Rendering
```

## Research Focus

- **Tool Use in LLMs:** How to structure tools for scientific discovery?
- **Multi-step Reasoning:** Can agents autonomously plan research workflows?
- **Evaluation Metrics:** How to measure "quality" of scientific reasoning?
- **Bias in Structure Prediction:** How does AlphaFold bias affect drug discovery predictions?

## Project Deliverables

1. ✅ Bio-Agent Python package with UniProt + AlphaFold + PDB tools
2. ✅ ReAct reasoning engine with LangChain
3. ✅ BioPython-based structure analysis module
4. ✅ Streamlit dashboard with real-time agent reasoning
5. ✅ Sample workflows (target validation, variant analysis, drug discovery)
6. ✅ Technical report: "Agentic Workflows for Scientific Data"
7. ✅ GitHub repository with documentation & examples
8. ✅ Deployment guide (Docker + cloud options)

## Technology Stack

- **Language:** Python (core)
- **LLM Framework:** LangChain or LlamaIndex
- **LLM Model:** OpenAI GPT-4, Claude, or Llama 3 (via Ollama)
- **Biology Tools:** BioPython, RDKit (chemistry)
- **APIs:** UniProt REST API, AlphaFold DB API
- **UI:** Streamlit (rapid), or React (advanced)
- **Visualization:** Py3Dmol (protein structures)
- **Deployment:** Docker, Streamlit Cloud, or AWS SageMaker

## Student Profile

**Preferred Disciplines:**
- Bioinformatics / Computational Biology
- AI & Machine Learning (with biology interest)
- Computer Science with biology background

**Prerequisites:**
- Proficiency in Python
- Understanding of protein structure basics
- Familiarity with APIs and REST calls
- Interest in AI + biology intersection

**Nice to Have:**
- BioPython experience
- Knowledge of molecular biology
- Experience with LangChain or LlamaIndex
- Familiarity with PDB file format
- Interest in drug discovery

## Project Timeline

**Total Duration:** 2-3 months

- **Week 1-2:** Tool layer (UniProt, AlphaFold APIs), API error handling
- **Week 3-4:** BioPython integration, pLDDT analysis
- **Week 5-6:** LangChain reasoning engine, ReAct patterns
- **Week 7-8:** Streamlit dashboard, visualization (Py3Dmol)
- **Week 9-10:** Testing on real biological queries, documentation
- **Week 11-12:** Optimization, technical report, deployment

## How This Contributes to GAIR Lab

Project Jigyasa demonstrates:
- **AI for Science:** Moving beyond general-purpose AI to domain-specific agents
- **Tool Use in LLMs:** Practical implementation of agentic workflows
- **Reproducibility:** Open-source tools for scientific research
- **Industry-Ready:** Architecture used by real drug discovery companies

## Publications & Impact

Potential outcomes:
- Blog series: "Building AI Agents for Science"
- Research paper: "Evaluating LLM-based Protein Analysis Agents"
- Open-source toolkit adopted by bioinformatics researchers
- Conference talk at AI + Biology venues (ICML-CompBio, NeurIPS-AI4Science)

## Real-World Context

This project mirrors workflows at:
- **DeepMind AlphaFold team** (structure prediction + validation)
- **Recursion Pharmaceuticals** (AI-driven drug discovery)
- **MIT-IBM Watson AI Lab** (scientific workflows)
- **EleutherAI** (open-source scientific AI)

## Support & Mentorship

- **Lab Director:** Prof. Ashutosh Bhatia
- **AI/ML Mentor:** Skillplot (LLM orchestration, deployment)
- **Biology Advisor:** (Optional) Domain expert for validation
- **Community:** GAIR Lab WhatsApp project group

## Getting Started

1. **Interested?** [Contact us]({{ '/contact/' | relative_url }}) with your GitHub and background
2. **Prep:** Explore AlphaFold DB, UniProt, and BioPython
3. **Onboard:** Join project group and access starter templates

---

**Project Status:** Active  
**Last Updated:** 2024  
**Questions?** [Reach out]({{ '/contact/' | relative_url }})
