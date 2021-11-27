---
layout: page
title: "Home"
class: home
---

# Hi, I'm Moritz Schüler

<div class="columns" markdown="1">

<div class="intro" markdown="1">
I currently pursue my masters in [Robotics, Cognition, Intelligence](https://www.tum.de/studium/studienangebot/detail/robotics-cognition-intelligence-master-of-science-msc) with focus on Machine Learning and Deep Learning at the [Technical University](https://www.tum.de/) <img width="30" height="15" src="/images/TUM Logo.png" alt="Tum Logo icon"> in Munich.

Some more info

</div>

<div class="me" markdown="1">
<picture>
  <source srcset='/images/Passbild.webp' type='image/webp' />
  <img
    src='/images/Passbild.jpg'
    alt='Picture of Me: Moritz Schüler'>
</picture>

{:.no-list}

- <a href="mailto:{{ site.email }}">{{ site.email }}</a>
</div>

</div>

During my bachelor at CSU Stuttgart, I was one of the leaders of the [Formula Student](https://www.formulastudent.de/fsg/) student program [DHBW Engineering](https://www.dhbw-engineering.de/). In 2017, I received my B.Eng. from [Cooperative State University Stuttgart](https://www.dhbw-stuttgart.de/). I was a scholar of the [Deutschlandstipendium](https://www.deutschlandstipendium.de/deutschlandstipendium/de/home/home_node.html). I have worked as an engineer at [Porsche AG](https://www.porsche.com/germany/). Details are in my [CV]({{ "/cv/" | relative_url }}).

## Featured Projects

<div class="featured-projects">
  {% assign sorted_projects = site.data.projects | sort: 'highlight' %}
  {% for project in sorted_projects %}
    {% if project.highlight %}
      {% include project.html project=project %}
    {% endif %}
  {% endfor %}
</div>
<a href="{{ "/projects/" | relative_url }}" class="button">
  <i class="fas fa-chevron-circle-right"></i>
  Show More Projects
</a>

## Featured Publications

<div class="featured-publications">
  {% assign sorted_publications = site.publications | sort: 'year' | reverse %}
  {% for pub in sorted_publications %}
    {% if pub.highlight %}
      <a href="{{ pub.pdf }}" class="publication">
        <strong>{{ pub.title }}</strong>
        <span class="authors">{% for author in pub.authors %}{{ author }}{% unless forloop.last %}, {% endunless %}{% endfor %}</span>.
        <i>{% if pub.venue %}{{ pub.venue }}, {% endif %}{{ pub.year }}</i>.
        {% for award in pub.awards %}<br/><span class="award"><i class="fas fa-{% if award == "Best Paper Award" %}trophy{% else %}award{% endif %}" aria-hidden="true"></i> {{ award }}</span>{% endfor %}
      </a>
    {% endif %}
  {% endfor %}
</div>

<a href="{{ "/publications/" | relative_url }}" class="button">
<i class="fas fa-chevron-circle-right"></i>
Show All Publications
</a>

<div class="news-travel" markdown="1">

<div class="news" markdown="1">
## Latest News

<ul>
{% for news in site.data.news limit:10 %}
  {% include news.html news=news %}
{% endfor %}
</ul>

</div>

<div class="travel" markdown="1">
## Latest Travel

<table>
<tbody>
{% assign future_travel = site.data.travel | where_exp:'item','item.start == null' %}
{% for travel in future_travel %}
  {% include travel.html travel=travel %}
{% endfor %}
{% assign sorted_travel = site.data.travel | where_exp:'item','item.start' | sort: 'start' | reverse %}
{% for travel in sorted_travel limit:10 %}
  {% include travel.html travel=travel %}
{% endfor %}
</tbody>
</table>

</div>

</div>
