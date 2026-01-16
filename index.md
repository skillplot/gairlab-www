---
layout: default
title: GAIR Lab
permalink: /
---

<div class="hero">
    <div class="hero-content">
        <img src="{{ '/assets/img/gair-logo-white.png' | relative_url }}" alt="GAIR Lab Logo" class="logo-hero">
        
        <h1>GAIR Lab</h1>
        <div class="tagline">Generative AI Research</div>
        <p class="subtitle">
            A collaborative research initiative advancing the frontiers of Generative AI and Agentic Intelligence
        </p>
        
        <div class="cta-buttons">
            <a href="{{ '/projects/' | relative_url }}" class="btn btn-primary">Explore Projects</a>
            <a href="{{ '/contact/' | relative_url }}" class="btn btn-secondary">Get in Touch</a>
        </div>
    </div>
</div>

<div class="section container">
    <div class="section-header">
        <h2>About GAIR Lab</h2>
        <p>Advancing research at the intersection of Generative AI, Agentic Systems, and Real-world Applications</p>
    </div>
    
    <div style="max-width: 900px; margin: 0 auto; text-align: center;">
        <p style="font-size: 1.125rem; color: #6B7280; line-height: 1.8;">
            GAIR Lab is a research initiative at BITS Pilani, established in collaboration with Skillplot, 
            focusing on cutting-edge research in Generative AI, Agentic Intelligence, and their applications 
            in cybersecurity, bioinformatics, multimodal intelligence, and creative technologies.
        </p>
        
        <p style="font-size: 1.125rem; color: #6B7280; line-height: 1.8; margin-top: 1.5rem;">
            Our mission is to conduct rigorous, publication-ready research while creating tangible 
            open-source tools and frameworks that benefit the broader research community.
        </p>
    </div>
</div>

<div class="section alt">
    <div class="container">
        <div class="section-header">
            <h2>Featured Projects</h2>
            <p>Current research initiatives under GAIR Lab</p>
        </div>
        
        <div class="cards-grid">
            {% assign projects = site.projects | sort: "title" | limit: 3 %}
            {% for project in projects %}
                <div class="card project-card">
                    <h3 class="project-title">{{ project.title }}</h3>
                    <p class="project-description">{{ project.brief_description | truncatewords: 25 }}</p>
                    
                    {% if project.disciplines %}
                        <div class="project-disciplines">
                            {% for discipline in project.disciplines | slice: 0, 2 %}
                                <span class="discipline">{{ discipline | truncatewords: 3 }}</span>
                            {% endfor %}
                        </div>
                    {% endif %}
                    
                    <a href="{{ project.url }}" class="card-link">Learn More <i class="fas fa-arrow-right"></i></a>
                </div>
            {% endfor %}
        </div>
        
        <div style="text-align: center; margin-top: 2rem;">
            <a href="{{ '/projects/' | relative_url }}" class="btn btn-outline">View All Projects</a>
        </div>
    </div>
</div>

<div class="section container">
    <div class="section-header">
        <h2>Lab Leadership</h2>
        <p>Meet the Principal Investigator and Lab Director</p>
    </div>
    
    <div class="cards-grid">
        {% assign people = site.people | where: "role", "PI" | limit: 1 %}
        {% for person in people %}
            <div class="card" style="text-align: center;">
                {% if person.image %}
                    <img src="{{ person.image | relative_url }}" alt="{{ person.name }}" 
                         style="width: 150px; height: 150px; border-radius: 50%; object-fit: cover; margin: 0 auto 1rem; border: 3px solid #D4A574;">
                {% endif %}
                <h3>{{ person.name }}</h3>
                <p class="text-gold" style="font-weight: 600; margin-bottom: 0.5rem;">{{ person.title }}</p>
                <p style="color: #6B7280; font-size: 0.95rem;">{{ person.affiliation }}</p>
                <a href="{{ person.url }}" class="card-link" style="margin-top: 1rem;">View Profile <i class="fas fa-arrow-right"></i></a>
            </div>
        {% endfor %}
    </div>
</div>

<div class="section alt">
    <div class="container">
        <div class="section-header">
            <h2>Why GAIR Lab?</h2>
            <p>Our commitment to excellence in research and innovation</p>
        </div>
        
        <div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 2rem; max-width: 1000px; margin: 2rem auto 0;">
            <div>
                <div style="font-size: 2rem; color: #00D9FF; margin-bottom: 1rem;">
                    <i class="fas fa-flask"></i>
                </div>
                <h4>Rigorous Research</h4>
                <p style="color: #6B7280;">Publication-ready research with peer-reviewed outcomes and open-source contributions</p>
            </div>
            
            <div>
                <div style="font-size: 2rem; color: #00D9FF; margin-bottom: 1rem;">
                    <i class="fas fa-code"></i>
                </div>
                <h4>Practical Tools</h4>
                <p style="color: #6B7280;">Open-source frameworks and implementations that solve real-world problems</p>
            </div>
            
            <div>
                <div style="font-size: 2rem; color: #00D9FF; margin-bottom: 1rem;">
                    <i class="fas fa-network-wired"></i>
                </div>
                <h4>Collaborative Ecosystem</h4>
                <p style="color: #6B7280;">Part of Skillplot's research ecosystem with industry partnerships and academia collaboration</p>
            </div>
            
            <div>
                <div style="font-size: 2rem; color: #00D9FF; margin-bottom: 1rem;">
                    <i class="fas fa-graduation-cap"></i>
                </div>
                <h4>Student Mentorship</h4>
                <p style="color: #6B7280;">Hands-on learning opportunities for students in cutting-edge AI research areas</p>
            </div>
            
            <div>
                <div style="font-size: 2rem; color: #00D9FF; margin-bottom: 1rem;">
                    <i class="fas fa-book"></i>
                </div>
                <h4>Knowledge Sharing</h4>
                <p style="color: #6B7280;">Documentation, blogs, and technical guides for the broader research community</p>
            </div>
            
            <div>
                <div style="font-size: 2rem; color: #00D9FF; margin-bottom: 1rem;">
                    <i class="fas fa-users"></i>
                </div>
                <h4>Open Community</h4>
                <p style="color: #6B7280;">Active WhatsApp communities and open channels for collaboration and discussion</p>
            </div>
        </div>
    </div>
</div>

<div class="section container">
    <div style="text-align: center; max-width: 800px; margin: 0 auto;">
        <h2>Join Our Community</h2>
        <p style="font-size: 1.125rem; color: #6B7280; margin-bottom: 2rem;">
            Are you interested in Generative AI research? Whether you're a student, researcher, or industry partner, 
            we welcome your interest and collaboration.
        </p>
        <a href="{{ '/contact/' | relative_url }}" class="btn btn-primary">Connect With Us</a>
    </div>
</div>
