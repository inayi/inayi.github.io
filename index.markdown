---
layout: page
---

<p class="projects-intro">Projects I'm building, exploring, or just dumping here to plan and implement later.</p>

<style>
  .projects-intro {
    text-align: center;
    color: #444;
  }
  .projects-grid {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 1.25rem;
    margin-top: 1.5rem;
  }
  .projects-grid .project-card {
    flex: 0 1 280px;
  }
  .projects-grid .project-card {
    border: 1px solid #e0e0e0;
    border-radius: 10px;
    padding: 1.1rem 1.2rem;
    background: #fff;
    display: flex;
    flex-direction: column;
    transition: box-shadow 0.15s ease, transform 0.15s ease;
  }
  .projects-grid .project-card:hover {
    box-shadow: 0 4px 14px rgba(0, 0, 0, 0.08);
    transform: translateY(-2px);
  }
  .projects-grid .project-head {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    gap: 0.5rem;
    margin-bottom: 0.6rem;
  }
  .projects-grid .project-title {
    font-size: 1.1rem;
    font-weight: 600;
    line-height: 1.3;
  }
  .projects-grid .project-title a { text-decoration: none; }
  .projects-grid .project-title a:hover { text-decoration: underline; }
  .projects-grid .project-desc {
    color: #444;
    font-size: 0.92rem;
    line-height: 1.5;
    margin: 0 0 0.9rem;
    flex-grow: 1;
  }
  .projects-grid .badge {
    display: inline-block;
    font-size: 0.7rem;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 0.03em;
    padding: 0.2rem 0.55rem;
    border-radius: 999px;
    white-space: nowrap;
    color: #fff;
  }
  .badge--idea        { background: #8e8e93; }
  .badge--planning    { background: #f0a020; }
  .badge--in-progress { background: #2b7de9; }
  .badge--done        { background: #2ea44f; }
  .projects-grid .project-notes {
    margin: 0 0 0.9rem;
    padding-left: 1.1rem;
    color: #444;
    font-size: 0.88rem;
    line-height: 1.5;
  }
  .projects-grid .project-notes li { margin-bottom: 0.25rem; }
  .projects-grid .project-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 0.35rem;
    margin-top: auto;
  }
  .projects-grid .tag {
    font-size: 0.72rem;
    background: #f0f0f2;
    color: #555;
    padding: 0.15rem 0.5rem;
    border-radius: 4px;
  }
</style>

<div class="projects-grid">
  {% for project in site.data.projects %}
  <div class="project-card">
    <div class="project-head">
      <div class="project-title">
        {% if project.link %}<a href="{{ project.link }}">{{ project.title }}</a>{% else %}{{ project.title }}{% endif %}
      </div>
      {% comment %}
      <span class="badge badge--{{ project.status }}">{{ project.status | replace: '-', ' ' }}</span>
      {% endcomment %}
    </div>
    <p class="project-desc">{{ project.description }}</p>
    {% if project.notes %}
    <ul class="project-notes">
      {% for note in project.notes %}<li>{{ note }}</li>{% endfor %}
    </ul>
    {% endif %}
    {% if project.tags %}
    <div class="project-tags">
      {% for tag in project.tags %}<span class="tag">{{ tag }}</span>{% endfor %}
    </div>
    {% endif %}
  </div>
  {% endfor %}
</div>
