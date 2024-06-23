---
title: Portfolio
permalink: /portfolio
---

<section class="projects">

    <ul class="filter-list">

    <li class="filter-item">
        <button class="active" data-filter-btn>All</button>
    </li>
    
    {% assign tags = site.data.portfolio | map: "tag" | uniq %}
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

        {% assign tags = site.data.portfolio | map: "tag" | uniq %}
        {% for tag in tags %}
        <li class="select-item">
            <button data-select-item>{{ tag }}</button>
        </li>
        {% endfor %}

    </ul>

    </div>

    <ul class="select-grid-list">

    {% for project-item in site.data.portfolio %}
    <li class="select-grid-item active" data-filter-item data-category="{{ project-item.tag | downcase }}">
        <a target="_blank" href="{{ project-item.link }}">

        <figure class="select-grid-item-img">
            <div class="select-grid-item-icon-box">
            <ion-icon name="eye-outline"></ion-icon>
            </div>

            <img src="{{ project-item.image }}" alt="{{ project-item.image_alt }}" loading="lazy">
        </figure>

        <h3 class="select-grid-item-title">{{ project-item.title }}</h3>

        <p class="select-grid-item-description">{{ project-item.date }}, {{ project-item.tag }}</p>

        </a>
    </li>
    {% endfor %}

    </ul>

</section>
