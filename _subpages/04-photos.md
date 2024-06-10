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

    {% for photo-item in site.data.photos %}
    <li class="project-item active" data-filter-item data-category="{{ photo-item.tag | downcase }}">
        <a href="{{ photo-item.link }}">

        <figure class="project-img">
            <div class="project-item-icon-box">
            <ion-icon name="eye-outline"></ion-icon>
            </div>

            <img src="/assets/photos/{{ photo-item.file }}" alt="{{ photo-item.alt }}" loading="lazy" data-photos-image>
        </figure>

        <h3 class="project-title" data-photos-alt>{{ photo-item.alt }}</h3>

        <p class="project-category" data-photos-tag>{{ photo-item.tag }}</p>

        </a>
    </li>
    {% endfor %}

    </ul>

</section>

<div class="modal-container" data-modal-container>

    <div class="overlay" data-overlay></div>

    <section class="photos-modal">

    <button class="modal-close-btn" data-modal-close-btn>
        <ion-icon name="close-outline"></ion-icon>
    </button>

    <div class="modal-img-wrapper">
        <figure class="modal-avatar-box">
        <img src="./assets/images/avatar-1.png" alt="Daniel lewis" width="80" data-modal-img>
        </figure>

        <img src="./assets/images/icon-quote.svg" alt="quote icon">
    </div>

    <div class="modal-content">

        <h4 class="h3 modal-title" data-modal-title>Daniel lewis</h4>

        <time datetime="2021-06-14">14 June, 2021</time>

        <div data-modal-text>
        <p>
            Richard was hired to create a corporate identity. We were very pleased with the work done. She has a
            lot of experience
            and is very concerned about the needs of client. Lorem ipsum dolor sit amet, ullamcous cididt
            consectetur adipiscing
            elit, seds do et eiusmod tempor incididunt ut laborels dolore magnarels alia.
        </p>
        </div>

    </div>

    </section>

</div>
