---
title: Photography
permalink: /photos
---

<section class="photos">

    <ul class="filter-list">

    <li class="filter-item">
        <button class="active" data-filter-btn>All</button>
    </li>
    
    {% assign tags = site.data.photos | map: "tag" | uniq %}
    {% for tag in tags %}
    <li class="filter-item">
        <button data-filter-btn>{{ tag }}</button>
    </li>
    {% endfor %}

    </ul>

    <div class="filter-select-box">

    <button class="filter-select" data-select>

        <div class="select-value" data-selecct-value>Select category</div>

        <div class="select-icon">
        <ion-icon name="chevron-down"></ion-icon>
        </div>

    </button>

    <ul class="select-list">

        <li class="select-item">
        <button data-select-item>All</button>
        </li>

        {% assign tags = site.data.photos | map: "tag" | uniq %}
        {% for tag in tags %}
        <li class="select-item">
            <button data-select-item>{{ tag }}</button>
        </li>
        {% endfor %}

    </ul>

    </div>

    <ul class="project-list">

    {% for project-item in site.data.photos %}
    <li class="project-item  active" data-filter-item data-category="{{ project-item.tag | downcase }}">
        <a href="{{ project-item.link }}">

        <figure class="project-img">
            <div class="project-item-icon-box">
            <ion-icon name="eye-outline"></ion-icon>
            </div>

            <img src="/assets/photos/{{ project-item.file }}" alt="{{ project-item.alt }}" loading="lazy">
        </figure>

        <h3 class="project-title">{{ project-item.tag }}</h3>

        <p class="project-category">{{ project-item.tag }}</p>

        </a>
    </li>
    {% endfor %}

    </ul>

</section>
