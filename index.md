---
layout: layout/default
title: Home
tags: home
---

# SPN Technical Infrastructure Group Emulation Resource

## Fans

<ul class="teaser-links">
  {%- for fan in collections.fan -%}
    <li>
      <h6>
        <a href="{{ fan.url }}">{{ fan.data.title }}</a>
      </h6>
      <p>{{ fan.data.description }}</p>
    </li>
  {%- endfor -%}
</ul>

## Power Supplies

<ul class="teaser-links">
  {%- for ups in collections.ups -%}
    <li>
      <h6>
        <a href="{{ ups.url }}">{{ ups.data.title }}</a>
      </h6>
      <p>{{ ups.data.description }}</p>
    </li>
  {%- endfor -%}
</ul>

## Scales

<ul class="teaser-links">
  {%- for scale in collections.scale -%}
    <li>
      <h6>
        <a href="{{ scale.url }}">{{ scale.data.title }}</a>
      </h6>
      <p>{{ scale.data.description }}</p>
    </li>
  {%- endfor -%}
</ul>

## About

I've copied the templates over from Does it Beep for now, we can change this but I've left it as an example...