---
name: kali
title: "Kali: Agentic Cyber-Defense"
brief_description: "Building an Autonomous AI Interface for Kali Linux - a conversational tool that translates natural language security requests into executable security operations"
status: Active
affiliation: "GAIR Lab × Skillplot @ BITS Pilani"
disciplines:
  - "Computer Science / Software Engineering"
  - "AI & Machine Learning / Cybersecurity"
  - "Systems & Infrastructure"
---

## Project Overview

As Generative AI evolves, the next frontier is **Agentic AI**—systems that don't just chat, but actively use tools to solve problems. Project Kali offers a unique opportunity to build an Agentic Cybersecurity Tool from the ground up. 

The goal is to **democratize access to powerful security testing** by creating a Conversational Web Interface that sits on top of the industry-standard Kali Linux operating system.

Currently, using security tools requires memorizing complex command-line syntax. In this 2-month internship, you will engineer a solution where a user can simply ask an AI agent to **"scan the network for open ports"** or **"check this API for vulnerabilities,"** and the system will autonomously execute the underlying Kali Linux tools to perform the task.

## Expected Outcomes

### Functional Web Application
A deployed React + Python application where a user can chat with the system to trigger at least 3 distinct security tools within the Docker container.

### Agentic Workflow Engine
A working backend module capable of taking a user intent (e.g., "Analyze this URL") and converting it into a structured command sequence without human intervention.

### Secure Sandbox Implementation
A configured Docker environment that ensures the AI agent executes commands safely within the containerized Kali instance.

### Technical Documentation
A comprehensive GitHub repository containing the source code, setup scripts, and a "How-to" guide for future developers to extend the tool.

## Key Engineering Modules

### 1. Environment Setup
Deploying and managing a Dockerized Kali Linux container on Ubuntu 24.04 LTS to serve as the "toolbox" for the AI agent.

### 2. Backend Development (Python)
Writing the orchestration logic that translates natural language prompts from the LLM (using Ollama for offline or APIs like Gemini/OpenAI) into executable Linux shell commands.

### 3. Frontend Development (React)
Using prompt-to-code methodologies to rapidly build a React-based UI/UX. The focus is on creating intuitive "Chat" and "Dashboard" interfaces.

### 4. Tool Integration
Wiring up specific security tools (e.g., Nmap for network, OWASP ZAP for web apps) to be triggered by the Agent.

## Technical Architecture

```
User Interface (React)
        ↓
  Chat API (FastAPI)
        ↓
  Orchestration Engine (Python)
        ↓
  Docker Container (Kali Linux)
        ↓
  Security Tools (Nmap, OWASP ZAP, etc.)
```

## Research Focus

- **Tool Use in LLMs:** How to effectively program LLMs to choose and execute security tools
- **Sandbox Safety:** Ensuring AI-driven command execution doesn't pose security risks
- **UX for Technical Tools:** Making complex security operations accessible through natural language
- **Offline AI Agents:** Exploring both online (Gemini/OpenAI) and offline (Ollama) LLM backends

## Project Deliverables

1. ✅ Dockerized Kali environment with orchestration logic
2. ✅ Python backend for LLM-to-command translation
3. ✅ React frontend with chat and dashboard UI
4. ✅ Integration of at least 3 security tools (Nmap, OWASP ZAP, Gobuster)
5. ✅ Comprehensive technical documentation & GitHub repository
6. ✅ Deployment guide for future teams

## Technology Stack

- **Frontend:** React 18, TypeScript, Tailwind CSS
- **Backend:** Python, FastAPI, Ollama (or OpenAI API)
- **Containerization:** Docker, Docker Compose
- **Security Tools:** Kali Linux, Nmap, OWASP ZAP, Gobuster
- **LLM Integration:** Ollama (local) / Gemini / OpenAI (cloud)

## Student Profile

**Preferred Disciplines:** 
- Computer Science / Software Engineering
- AI & Machine Learning with cybersecurity focus
- Systems Engineering / DevOps

**Prerequisites:**
- Strong Python programming (core language for backend)
- Familiarity with React or willingness to learn quickly
- Understanding of cybersecurity concepts (not expert-level, but fundamentals)
- Comfortable with CLI and Docker

**Nice to Have:**
- Experience with FastAPI or similar Python frameworks
- Knowledge of Kali Linux or penetration testing tools
- LLM/prompt engineering experience

## Project Timeline

**Total Duration:** 2-3 months (depending on internship structure)

- **Week 1-2:** Environment setup, Docker orchestration, initial LLM integration
- **Week 3-4:** Backend framework build-out, tool integration with Nmap
- **Week 5-6:** Frontend scaffolding, chat interface
- **Week 7-8:** Full integration, testing, documentation
- **Week 9-10:** Optimization, additional tools, final deployment

## How This Contributes to GAIR Lab

Project Kali is a **proof-of-concept for Agentic AI** in a highly practical, security-focused domain. Successful completion will demonstrate:
- How autonomous AI can orchestrate complex system operations
- The feasibility of tool-use in LLMs for real-world applications
- A reusable framework that can be adapted for other domains (data analysis, DevOps, etc.)

## Support & Mentorship

- **Lab Director:** Prof. Ashutosh Bhatia (available for guidance on architecture and security concerns)
- **Skillplot Technical Mentor:** Code reviews, DevOps guidance, deployment support
- **Community:** GAIR Lab WhatsApp project group for real-time discussion

## Getting Started

1. **Interested?** [Contact GAIR Lab]({{ '/contact/' | relative_url }}) with your GitHub profile and brief intro
2. **Explore:** Clone our [starter repositories](https://github.com/skillplot/gairlab) for setup examples
3. **Join:** Once onboarded, you'll be added to the project WhatsApp group for collaboration

---

**Project Status:** Active  
**Last Updated:** 2024  
**Questions?** [Reach out to us]({{ '/contact/' | relative_url }})
