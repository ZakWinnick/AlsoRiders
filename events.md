---
layout: page
title: Events
eyebrow: Where and when
lede: Group rides, meetups, and gatherings. Posted as they're scheduled. Everything RSVPs through Heylo.
permalink: /events/
---

<!--
  Once you're on Heylo Pro, replace the block below with the embed snippet
  Heylo gives you in Group Admin → Website embed. It'll auto-sync events
  from your group and inherit the site's typography.
-->

{% if site.data.events.events.size > 0 %}
<ul class="event-list">
  {% for event in site.data.events.events %}
    <li>
      <span class="event-date">{{ event.date }}</span>
      <div>
        <p class="event-title">{{ event.title }}</p>
        <p class="event-meta">{{ event.location }}{% if event.region %} · {{ event.region }}{% endif %}</p>
      </div>
      <a class="mono" href="{{ event.url | default: site.heylo_url }}" target="_blank" rel="noopener">RSVP →</a>
    </li>
  {% endfor %}
</ul>
{% else %}
<div class="events-empty">
  <p class="eyebrow">No events scheduled yet</p>
  <h3>The first wave of rides is coming together.</h3>
  <p>First TM-B deliveries are happening now. As owners surface in different cities, we're scheduling kickoff rides region by region. Join on Heylo to add your metro area and you'll get a notification the moment something's on the calendar near you.</p>
  <a class="btn" href="{{ site.heylo_url }}" target="_blank" rel="noopener">{{ site.heylo_label }} <span class="arrow">→</span></a>
</div>
{% endif %}

## Want to host one?

If you've got an ALSO and a route you love, host a ride. Message a club admin on Heylo and we'll help you set it up, promote it in the right regional chat, and put it on the calendar here. You don't need to be the first owner in your city for long — you just need to show up first.
