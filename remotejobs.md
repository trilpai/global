---
layout: default
title: Global Remote Jobs
---

<h2 class="text-xl font-semibold mt-8 mb-2">🌍 Explore Global Opportunities</h2>

Curated guides for Indian software developers (ages 21–25) exploring remote and onsite overseas careers.

{% assign grouped = site.remotejobs | group_by: 'continent' %}
{% for continent in grouped %}
<br>

<h2 class="text-xl font-semibold mt-8 mb-2">🌐 {{ continent.name }}</h2>

{% assign sorted_countries = continent.items | sort: 'remote_rank' %}

<div class="grid gap-4 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 mt-4 mb-8">
  {% for country in sorted_countries %}
    <a href="{{ country.url | relative_url }}" class="p-4 hover:bg-gray-50">
      <span class="text-lg font-semibold">{{ country.emoji_flag }} {{ country.title }}</span>
    </a>
  {% endfor %}
</div>
{% endfor %}
