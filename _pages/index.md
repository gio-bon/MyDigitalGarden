---
layout: page
title: Home
id: home
permalink: /
---

Este é meu [digital garden](https://youtu.be/i8EwNnO9Uks), escrito com [obsidian](https://obsidian.md)e inspirado na ideia de [Learn in Public](https://segredo.dev/aprenda-em-publico/). <br>

- <a class="internal-link" href="/about">Sobre mim</a> 🧑‍💻
- [[Projetos]] 🚧 	
- [[Estudos]] 🧠 <br>

<div>
  <div class="grid-element">
    <h2>Blog posts</h2>
    {% assign post_limit = 7 %}
    {% for post in site.posts limit: post_limit %}
    <div class="list-entry">
      <div><a class="internal-link" href="{{ post.url }}">{{ post.title }}</a> <span class="faded">({{ post.date | date: "%Y-%m-%d" }})</span></div>
      <div>{{ post.excerpt }}</div>
    </div>
    {% endfor %}
    <p>
      <a class="internal-link" href="/blog">I wrote {{ site.posts.size | minus: post_limit }} more posts</a>.
      This blog is also available as <a class="internal-link" target="_blank" href="/rss.xml">RSS</a> and <a class="internal-link" target="_blank" href="/feed.json">JSON</a> feeds.
    </p>
  </div>

Explore meu <a class="internal-link" href="/map">mapa de notas.</a> 🗺️ <br>
