---
title: About
permalink: /
---

<section class="about-text">
    {{ site.data.profile.about | markdownify }}
</section>


<!--
    - service
-->

<section class="service">

    <h3 class="h3 service-title">What I'm Doing</h3>

    <ul class="service-list">

    {% for service-item in site.data.current-projects %}
    <li class="service-item">

        <div class="service-icon-box">
        <img src="{{ service-item.icon }}" alt="{{ service-item.icon_alt }}" width="40">
        </div>

        <div class="service-content-box">
        <h4 class="h4 service-item-title">{{ service-item.title }}</h4>

        <p class="service-item-text">
            {{ service-item.description | markdownify }}
        </p>
        </div>

    </li>
    {% endfor %}

    </ul>

</section>


<!--
    - testimonials
-->

<section class="testimonials">

    <h3 class="h3 testimonials-title">What Else?</h3>

    <ul class="testimonials-list has-scrollbar">

    {% for testimonial in site.data.testimonials %}
    <li class="testimonials-item">
        <div class="content-card" data-testimonials-item>

        <figure class="testimonials-avatar-box">
            <img src="{{ testimonial.icon }}" alt="{{ testimonial.icon_alt }}" width="60" data-testimonials-avatar>
        </figure>

        <h4 class="h4 testimonials-item-title" data-testimonials-title>{{ testimonial.title }}</h4>

        <div class="testimonials-text" data-testimonials-text>
            {{ testimonial.content | markdownify }}
        </div>

        </div>
    </li>
    {% endfor %}

    </ul>

</section>


<!--
    - testimonials modal
-->

<div class="modal-container" data-modal-container>

    <div class="overlay" data-overlay></div>

    <section class="modal testimonials-modal">

    <button class="modal-close-btn" data-modal-close-btn>
        <ion-icon name="close-outline"></ion-icon>
    </button>

    <div class="modal-img-wrapper">
        <figure class="modal-avatar-box">
        <img src="/assets/images/cybersec.svg" alt="" width="80" data-modal-img>
        </figure>
    </div>

    <div class="modal-content">

        <h4 class="h3 modal-title" data-modal-title></h4>

        <div data-modal-text></div>

    </div>

    </section>

</div>


<!--
    - clients
-->

<section class="clients">

    <h3 class="h3 clients-title">Clients & Employers</h3>

    <ul class="clients-list has-scrollbar">

    {% for client in site.data.clients %}
    <li class="clients-item">
        <a target="_blank" href="{{ client.link }}">
        <img src="{{ client.logo }}" alt="{{ client.company }}">
        </a>
    </li>
    {% endfor %}

    </ul>

</section>
