---
title: Résumé
permalink: /resume
---

<section class="timeline">

    <div class="title-wrapper">
    <div class="icon-box">
        <ion-icon name="book-outline"></ion-icon>
    </div>

    <h3 class="h3">Education</h3>
    </div>

    <ol class="timeline-list">

    {% for education-item in site.data.education %}
    <li class="timeline-item">

        <h4 class="h4 timeline-item-title">{{ education-item.institution }}</h4>

        <span>{{ education-item.start_year }} — {{ education-item.end_year }} ({{ education-item.grade }})</span>
        
        <p class="timeline-text">
            {{ education-item.description | markdownify }}
        </p>

    </li>
    {% endfor %}

    </ol>

</section>

<section class="timeline">

    <div class="title-wrapper">
    <div class="icon-box">
        <ion-icon name="book-outline"></ion-icon>
    </div>

    <h3 class="h3">Experience</h3>
    </div>

    <ol class="timeline-list">

    {% for experience-item in site.data.experience %}
    <li class="timeline-item">

        <h4 class="h4 timeline-item-title">{{ experience-item.job_title }}{% if experience-item.company %}, {{ experience-item.company }}{% endif %}</h4>

        <span>{{ experience-item.start_year }} — {{ experience-item.end_year }}</span>

        {% if experience-item.description %}
        <p class="timeline-text">
        {{ experience-item.description | markdownify }}
        </p>
        {% endif %}

    </li>
    {% endfor %}

    </ol>

</section>

<section class="skill">

    <h3 class="h3 skills-title">My skills</h3>

    <ul class="skills-list content-card">

    {% for skill in site.data.skills %}
    <li class="skills-item">

        <div class="title-wrapper">
        <h5 class="h5">{{ skill.name }}</h5>
        <data value="{{ skill.value }}"></data>
        </div>

        <div class="skill-progress-bg">
        <div class="skill-progress-fill" style="width: {{ skill.value }}%;"></div>
        </div>

    </li>
    {% endfor %}

    </ul>

</section>
