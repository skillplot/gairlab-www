---
name: drishti
title: "Drishti: Agentic Multimodal Intelligence for National Security"
brief_description: "Building an Agentic AI System powered by Vision-Language Models that autonomously analyzes surveillance data and constructs Space-Time understanding of threats"
status: Planned
affiliation: "GAIR Lab × Skillplot @ BITS Pilani"
disciplines:
  - "AI & Machine Learning (Computer Vision focus)"
  - "Data Science / Video Intelligence"
  - "Software Engineering / Systems"
---

## Project Overview

In the domain of **National Security**, analysts are drowning in unstructured data—live surveillance streams, intercepted videos, and field reports. The challenge is no longer "gathering" data, but **"connecting the dots" in real-time**.

**Project Drishti** aims to build an **Agentic AI System** powered by **Qwen2.5-VL** (a state-of-the-art Vision-Language Model) that **autonomously watches, reads, and listens** to diverse data sources to construct a **"Space-Time" understanding of threats**.

This is **not just a video search tool**; it is a **Multimodal Reasoning Engine**. You will engineer an AI agent capable of:
- **Visual Grounding:** Locating specific entities or actions in space and time
- **Temporal Reasoning:** Understanding cause-effect relationships between events
- **Semantic Linking:** Mapping events into a structured "Intelligence Ontology"

Analysts can then query this system using natural language: *"Show me all interactions involving the red van"* or *"Find instances of suspicious meetings on this street."*

## Expected Outcomes

### Drishti Core Engine
A **Dockerized Python service** capable of:
- Ingesting RTSP streams (live or recorded video)
- Processing frames using Qwen2.5-VL
- Outputting structured JSON logs with:
  - **Temporal bounding boxes** (when did the event occur?)
  - **Spatial coordinates** (where in the frame?)
  - **Semantic labels** (what happened?)
  - **Confidence scores** (how certain is the model?)

### The "Ops" Dashboard
A deployed web application where analysts can:
- Upload video evidence or access live feeds
- Visualize the "Space-Time Graph" as interactive clusters
- Query events using natural language
- Download evidence and reports

### A "Watchdog" Pipeline
A functioning script that:
- Monitors mock video feeds in real-time
- Automatically flags anomalies into a structured log
- Triggers alerts for high-confidence security events

### Technical Report
**"Building Multimodal RAG Systems for Video Intelligence"**—a comprehensive guide for future researchers on architecting similar systems.

## Key Engineering Modules

### 1. Technology Evaluation (The Experiment)

You will benchmark **Qwen2.5-VL** against traditional pipelines for three critical tasks:

#### Task A: Temporal Grounding
**Question:** Can the model identify *exactly when* an event starts and stops?  
**Example:** "Find the moment the fighting starts" → Output: `{start_frame: 245, end_frame: 892, timestamp: "00:14:30 - 00:45:10"}`  
**Benchmark Dataset:** UCF-Crime

#### Task B: Dense Captioning
**Question:** Can it generate second-by-second textual logs of long-form video?  
**Example:** 
```
00:00 - Two people enter the room
00:05 - Conversation begins
00:15 - [ALERT] Suspicious exchange
00:20 - Individual leaves hastily
```
**Benchmark Dataset:** ActivityNet Captions

#### Task C: Spatial Coordinates
**Question:** Can it output JSON bounding boxes to pinpoint *where* an object is?  
**Example:**
```json
{
  "frame": 500,
  "objects": [
    {"type": "person", "bbox": [123, 456, 180, 600], "confidence": 0.95},
    {"type": "vehicle", "bbox": [50, 100, 300, 250], "confidence": 0.88}
  ]
}
```
**Benchmark Dataset:** MEVA

**Deliverable:** Technical report: *"Benchmarking VLM Efficiency in Surveillance: Qwen2.5 vs. Traditional CNNs"*

### 2. Real-World Use Cases & Datasets (7 Scenarios)

To ensure a functional, real-world prototype:

| Use Case | Dataset | Task |
|----------|---------|------|
| **Anomaly Detection** | UCF-Crime | Detect "abuse" or "fighting" |
| **Multi-View Tracking** | MEVA | Track a subject across multiple angles |
| **Forensic Retrieval** | VIRAT | "Find the moment the red car turns left" |
| **Dense Captioning** | ActivityNet Captions | Generate detailed event logs |
| **Person Search** | PA-100K, Market-1501 | "Locate the person in the white hat" |
| **Audio-Visual Correlation** | AVE Dataset | Correlate shouting with visual data |
| **Night Vision Analysis** | DarkVid, MEVA Thermal | Identify threats in low light |

You will develop working pipelines for **at least 3** of these scenarios.

### 3. The Space-Time Ontology (The Logic)

Build the backend logic to convert Qwen2.5-VL outputs into a **Temporal Knowledge Graph**:

Instead of simple storage, engineer **"Space-Time Bubbles":**
- Each detected event = 1 node in the graph
- Nodes are automatically linked if they share:
  - Same subject (person/vehicle)
  - Similar location (within threshold)
  - Overlapping time window
  - Semantic similarity

**Example Graph:**
```
[Event: Person A enters store] 
        ↓ (same person, 2 min later)
[Event: Person A makes purchase]
        ↓ (same person, 5 min later)
[Event: Person A meets Person B outside]
        ↓ (same location, 1 min later)
[Event: Exchange of package]
```

**Technology:** Neo4j (graph DB) or NetworkX (Python)

### 4. The War Room Interface (The UI)

Create a **"Chat with Reality"** dashboard using **React** or **Streamlit** where:
- Analysts upload video/text evidence
- Ask natural language queries:
  - *"Show me all interactions with the red van"*
  - *"Find instances of suspicious meetings"*
  - *"Timeline of events involving Subject #42"*
- System returns:
  - Video timestamps with bounding boxes
  - Related events from the Space-Time Graph
  - Confidence scores and risk assessments

## Technical Architecture

```
Video Input (RTSP / Upload)
        ↓
Frame Extraction & Preprocessing
        ↓
Qwen2.5-VL Processing
        ↓
Output: {temporal, spatial, semantic data}
        ↓
Neo4j Graph Construction
        ↓
Query Engine (NLP → Graph Query)
        ↓
Web Dashboard (React/Streamlit)
```

## Research Focus

- **Vision-Language Models for Surveillance:** Can Qwen2.5-VL match or exceed traditional CNNs?
- **Temporal Reasoning:** How to program automatic temporal linking of events?
- **Knowledge Graphs for Video:** Emerging research area; low baseline to beat
- **Privacy & Ethics:** How to responsibly deploy such a system?

## Project Deliverables

1. ✅ Qwen2.5-VL benchmark against 7 use cases
2. ✅ Dockerized Drishti Core Engine
3. ✅ Neo4j Space-Time Graph implementation
4. ✅ Query engine (NLP to graph queries)
5. ✅ React or Streamlit dashboard
6. ✅ "Watchdog" pipeline for real-time monitoring
7. ✅ Technical report: "Building Multimodal RAG Systems"
8. ✅ Sample outputs on benchmark datasets

## Technology Stack

- **Vision-Language Model:** Qwen2.5-VL (or similar)
- **Language:** Python (backend), JavaScript/React (frontend)
- **Graph Database:** Neo4j or NetworkX
- **Video Processing:** OpenCV, FFmpeg
- **Framework:** FastAPI (backend), React (frontend)
- **Deployment:** Docker, Docker Compose
- **Optional:** Streamlit (for rapid prototyping)

## Student Profile

**Preferred Disciplines:**
- AI/ML with strong Computer Vision focus
- Data Science / Machine Learning
- Software Engineering (systems design)
- Computational Mathematics

**Prerequisites:**
- Proficiency in Python
- Understanding of computer vision (CNNs, object detection, tracking)
- Experience with deep learning frameworks (PyTorch/TensorFlow)
- Comfortable with graph databases or graph theory
- Interest in real-world security applications

**Nice to Have:**
- Experience with video processing (OpenCV)
- Knowledge of tracking algorithms (Kalman filters, DeepSORT)
- Familiarity with Neo4j or graph databases
- Experience with deploying ML models

## Project Timeline

**Total Duration:** 3-4 months (longer due to complexity)

- **Week 1-2:** Literature review, Qwen2.5-VL setup, dataset exploration
- **Week 3-4:** Temporal grounding & dense captioning pipelines
- **Week 5-6:** Spatial coordinate extraction, benchmark report
- **Week 7-9:** Neo4j ontology & graph construction
- **Week 10-11:** Query engine & NLP interface
- **Week 12-13:** Dashboard development & integration
- **Week 14-16:** Testing, optimization, documentation

## How This Contributes to GAIR Lab

Project Drishti is **cutting-edge research** in:
- **Multimodal AI:** Combining vision, language, and reasoning
- **Knowledge Graphs from Video:** Emerging frontier in video understanding
- **Agentic Systems:** Autonomous anomaly detection and reasoning
- **Real-world Impact:** Security applications with tangible deployments

## Publications & Impact

Potential outcomes:
- Conference paper: "Qwen2.5-VL for Temporal Grounding in Surveillance Video"
- Technical blog series on Video Intelligence
- Open-source Drishti framework for researchers
- Adoption by security/law enforcement institutions

## Ethical Considerations

This project involves surveillance and security applications. We commit to:
- Transparency in model capabilities and limitations
- Privacy-respecting data handling (anonymized datasets)
- Clear documentation of bias and failure modes
- Responsible disclosure of findings

## Support & Mentorship

- **Lab Director:** Prof. Ashutosh Bhatia
- **AI/ML Mentor:** Skillplot (deep learning, deployment)
- **Security Expert:** Industry advisor (threat modeling, real-world scenarios)
- **Community:** GAIR Lab WhatsApp project group

## Getting Started

1. **Interested?** [Contact us]({{ '/contact/' | relative_url }}) with your CV and GitHub profile
2. **Prep:** Familiarize yourself with vision-language models (CLIP, LLaVA, Qwen)
3. **Onboard:** Once confirmed, join project WhatsApp and access starter code

---

**Project Status:** Planned (recruiting soon)  
**Estimated Start:** Next recruitment cycle  
**Questions?** [Reach out]({{ '/contact/' | relative_url }})
