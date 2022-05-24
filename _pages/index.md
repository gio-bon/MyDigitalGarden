---
layout: default copy
title: Home
id: home
permalink: /
---

<div>
  <div>
    <h1>
      Olá! Sou o <a class="internal-link" href="/about">Giovani</a>. Eu sou um dev. 👨‍💻
    </h1>
  </div>

<div>
  <div class="grid-element">
    <h2>✉️Postagens</h2>
    {% assign post_limit = 7 %}
    {% for post in site.posts limit: post_limit %}
    <div class="list-entry">
      <div><a class="internal-link" href="{{ post.url }}">{{ post.title }}</a> <span class="faded">({{ post.date | date: "%d-%m-%Y" }})</span></div>
      <div>{{ post.excerpt }}</div>
    </div>
    {% endfor %}
    <p>
      <a class="internal-link" href="/blog">Escrevi mais {{ site.posts.size | minus: post_limit }} postagens</a>.
    </p>
  </div>

  <div class="grid-element">
    <h2>🚧</i>Projetos</h2>

    {% assign project_limit = 2 %}
    {% for project in site.data.projects limit: project_limit %}
    <div class="list-entry">
      <div><a target="_blank" rel="noopener" href="{{ project.url }}">{{ project.name }}</a> <span class="faded">({{ project.date | date: "%d-%m-%Y" }})</span></div>
      <div>{{ project.description_html }}</div>
    </div>
    {% endfor %}

    {% assign additional_projects = site.data.projects.size | minus: project_limit %}
    {% if additional_projects > 0 %}
    <div>
      <p>
        <a class="internal-link" href="/projects">
          Veja mais ({{ additional_projects }} projetos)
        </a>
      </p>
    </div>
    {% endif %}
  </div>
</div>
