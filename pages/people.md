---
layout: page
title: Lab Members & People
permalink: /people/
---

GAIR Lab is built on the collaborative efforts of dedicated researchers, mentors, and contributors.

## Principal Investigator

<div class="cards-grid">
{% assign pi = site.people | where: "role", "PI" %}
{% for person in pi %}
    <div class="card" style="text-align: center;">
        {% if person.image %}
            <img src="{{ person.image | relative_url }}" alt="{{ person.name }}" 
                 style="width: 180px; height: 180px; border-radius: 50%; object-fit: cover; margin: 0 auto 1rem; border: 4px solid #D4A574;">
        {% else %}
            <div style="width: 180px; height: 180px; border-radius: 50%; margin: 0 auto 1rem; background-color: #D4A574; display: flex; align-items: center; justify-content: center; color: white; font-size: 4rem;">
                <i class="fas fa-user"></i>
            </div>
        {% endif %}
        
        <h3>{{ person.name }}</h3>
        <p class="text-gold" style="font-weight: 600;">{{ person.title }}</p>
        <p style="color: #6B7280;">{{ person.affiliation }}</p>
        
        <a href="{{ person.url }}" class="btn btn-outline" style="margin-top: 1rem; display: inline-block;">
            View Full Profile
        </a>
    </div>
{% endfor %}
</div>

## Contributors

GAIR Lab is supported by students, collaborators, and researchers from BITS Pilani and partner institutions.

**Current Students & Interns:** Details available on individual project pages.

**Advisors & Collaborators:** Affiliated researchers and institutional partners contribute to project guidance and mentorship.

---

## Get Involved

Are you interested in joining GAIR Lab as a student researcher or collaborator?

- **Students:** Check our [projects page]({{ '/projects/' | relative_url }}) for internship and research opportunities
- **Collaborators:** [Contact us]({{ '/contact/' | relative_url }}) to discuss research partnerships
- **Industry Partners:** Explore sponsorship and collaboration opportunities

