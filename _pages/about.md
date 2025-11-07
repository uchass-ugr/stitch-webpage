---
layout: about
title: Home
permalink: /
nav: true
nav_rank: 1
sitetitle: true
description: Welcome!

profile:
    name: 
    position: 
    align: right
    image: stitch-logo.jpg
    href: 
    email: 
    address: >
        
        

news: true # includes a list of news items
projects: false # includes a tile list of projects
supports: false # includes a tile list of supports
selected_papers: True # includes a list of papers marked as "selected={true}"
social: false  # includes social icons at the bottom of the page
---
The **STITCH Project (Scientific Teams and InequaliTies: Collaboration and Heterogeneity in Science)** explores how the **internal organization of scientific teams** influences **knowledge production** and contributes to **inequalities** within the global research system. Through an **interdisciplinary approach** combining sociological theory, bibliometrics, and data science, the project seeks to understand the social and structural mechanisms that drive scientific collaboration, innovation, and impact.

Using a unique dataset of **over 700,000 bibliographic records** with contribution statements (CRediT taxonomy) and **advanced machine learning techniques**, STITCH analyzes patterns of labor distribution within research teams, disciplinary differences, and inequalities related to gender, geography, and career stage.

Ultimately, the project aims to generate **robust empirical evidence** to inform **fairer and more inclusive science policies and evaluation frameworks**. By recognizing the collaborative and diverse nature of modern science, STITCH contributes to the **development of research systems that are more equitable, transparent, and socially responsive**.


{% assign members = site.members | where: "team_frontpage", true | sort: "lastname" %}
<div class="text-center pt-5">
  <h2>TEAM</h2>
</div>
<div class="d-flex flex-wrap align-content-stretch justify-content-center m-n2 pt-5 no-gutters">
    {% for member in members %}
        {% assign colsMod6 = forloop.length | modulo: 6 %}
        {% assign colIdMod4 = forloop.index | modulo: 4 %}
        {% if colsMod6 == 1 and colIdMod4 == 1 %}<div class="col-md-2 w-100"></div>{% endif %}
        <div class="col-6 col-sm-3 col-md-2 mb-3">
            <a href="{{ member.url | relative_url }}" class="no-decoration">
                <div class="card hoverable h-100 m-2">
                    <img src="{{ '/assets/img/' | append: member.profile.image | relative_url }}" class="card-img-top" alt="{{ member.profile.name }}" />
                    <div class="card-body p-2">
                        <div class="card-title m-0">{{ member.title }}</div>
                    </div>
                </div>
            </a>
        </div>
    {% endfor %}
</div>
