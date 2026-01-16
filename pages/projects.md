---
layout: page
title: Research Projects
permalink: /projects/
---

GAIR Lab is currently conducting research across multiple cutting-edge domains. Each project combines rigorous academic research with practical, open-source implementations.

## Active Projects

<div class="cards-grid" style="margin-top: 2rem;">
{% assign projects = site.projects | sort: "title" %}
{% for project in projects %}
    <div class="card project-card">
        <h3 class="project-title">{{ project.title }}</h3>
        
        {% if project.brief_description %}
            <p class="project-description">{{ project.brief_description }}</p>
        {% endif %}
        
        {% if project.status %}
            <p style="font-size: 0.85rem; color: #6B7280; margin-bottom: 1rem;">
                <strong>Status:</strong> 
                <span class="tag" style="background-color: 
                    {% if project.status == 'Active' %}rgba(0, 217, 255, 0.2); color: #00D9FF;
                    {% elsif project.status == 'Planned' %}rgba(212, 165, 116, 0.2); color: #D4A574;
                    {% else %}rgba(107, 114, 128, 0.2); color: #6B7280;
                    {% endif %}
                ">{{ project.status }}</span>
            </p>
        {% endif %}
        
        {% if project.disciplines %}
            <div class="project-disciplines">
                {% for discipline in project.disciplines | slice: 0, 2 %}
                    <span class="discipline">{{ discipline }}</span>
                {% endfor %}
            </div>
        {% endif %}
        
        <a href="{{ project.url }}" class="card-link" style="margin-top: 1rem;">
            View Project Details <i class="fas fa-arrow-right"></i>
        </a>
    </div>
{% endfor %}
</div>

## Project Categories

### AI & Cybersecurity
Research at the intersection of Generative AI and cybersecurity, building agentic systems for security automation.

### Multimodal AI
Advanced work on Vision-Language Models and their applications in real-world scenarios like surveillance and intelligence analysis.

### Creative AI & Audio
Exploration of voice cloning, emotion synthesis, and creative applications of AI in content generation.

### Scientific AI
Using AI agents for accelerating scientific discovery in domains like bioinformatics and drug discovery.

---

## Looking to Collaborate?

If you're interested in joining a project, supporting research, or exploring collaboration opportunities, please [contact us]({{ '/contact/' | relative_url }}).

**For Students:** GAIR Lab offers internship opportunities during academic breaks. Check individual project pages for details.

**For Institutions & Industry:** We welcome research partnerships and sponsorships. [Get in touch]({{ '/contact/' | relative_url }}) to discuss collaboration.
