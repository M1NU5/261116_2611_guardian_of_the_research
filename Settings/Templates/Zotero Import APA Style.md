---
title: "{{ title | default('Untitled') }}"

authors:
{% for creator in creators %}
  - "[[{{ creator.lastName }}, {{ creator.firstName | first | upper }}.]]"
{% endfor %}

year: "{% if date %}{{ date | format('YYYY') }}{% else %}n.d.{% endif %}"

citation-key: "{{ citekey | default(citationKey | default('')) }}"

source: "{{ zoteroSelectURI | default('') }}"

apa-reference: "{{ bibliography | replace('\n', ' ') | trim }}"

publisher: "{{ publicationTitle | default(publisher | default('')) }}"

doi: "{{ DOI | default('') }}"

tags:
  - zotero-import
{% for tag in tags %}
  - "{{ tag.tag | replace(' ', '-') | lower }}"
{% endfor %}
---

# Key Point

-

# Problem

- What problem is this paper addressing?
- Why is the problem important?
- What gap does the paper identify?

# Theory

- What theories, models, or conceptual frameworks are used?
- What mechanisms are proposed to explain the phenomenon?
- [[]]

# Mechanics

- What design elements, game mechanics, or features are investigated?
- How are they expected to influence behaviour or cognition?
- [[]]

# Intervention

- What intervention, system, artefact, or implementation is studied?
- How was it implemented?
- [[]]

# Methods

- Research design:
- Participants / sample:
- Data collection:
- Measures:
- Analysis:
- [[]]

# Results

- What are the main findings?
- What relationships or effects were observed?
- Were the hypotheses supported?

# Relevance

- How does this relate to my research?
- Which research question does it inform?
- How could I use/cite this paper?
- Connections to other literature:
- [[]]

# Notes

{% for annotation in annotations %}
{% if annotation.annotatedText %}
> [!quote]+ <span style="color: {{ annotation.color }};">Citation{% if annotation.pageLabel %} — Page {{ annotation.pageLabel }}{% endif %}</span>
>
> {{ annotation.annotatedText | safe }}
{%- if annotation.tags and annotation.tags.length > 0 %}
>
> {% for tag in annotation.tags %}#{{ tag.tag | replace(' ', '-') | lower }}{% if not loop.last %} {% endif %}{% endfor %}
{%- endif %}
{%- if annotation.comment %}
>
> **Personal Note**
>
> - {{ annotation.comment | safe }}
{%- endif %}

{% endif %}
{% endfor %}

{% if notes and notes.length > 0 %}

## Zotero Notes

{% for note in notes %}

### Zotero Note

- {{ note.note | safe }}

{% endfor %}

{% endif %}

# Citation (APA 7th style)

{{ bibliography | safe }}