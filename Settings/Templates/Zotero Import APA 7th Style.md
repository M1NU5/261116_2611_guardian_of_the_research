---
title: "{{ title | default('Untitled') }}"
authors:
{% for creator in creators %}
  - "[[{{ creator.lastName }}, {{ creator.firstName | first | upper }}.]]"
{% endfor %}
year: "{% if date %}{{ date | format('YYYY') }}{% else %}n.d.{% endif %}"
citation-key: "{{ citekey | default(citationKey | default('')) }}"
source: "{{ zoteroSelectURI | default('') }}"
gemini-notebook-url: ""
apa-reference: "{{ bibliography | replace('\n', ' ') | trim }}"
publisher: "{{ publicationTitle | default(publisher | default('')) }}"
doi: "{{ DOI | default('') }}"
tags:
  - zotero-import
  - flashcards
  - "flashcards/{{ citekey }}"
{% for tag in tags %}
  - "{{ tag.tag | replace(' ', '-') | lower }}"
{% endfor %}
---

---
---
# Key Point
 -
  

---
---
# Data Extraction
## 1. Problem
- What problem is this paper addressing?
	- Digital workplace fragmentation
	- Context switching
	- Interruptions
	- Distributed information
	- Multiple goals
	- Application switching
	- Attention residue
	- Difficulty translating goals into digital actions
	- Cognitive effort associated with digital work

{%- for annotation in annotations %}

{%- set isMatch = false %}

{%- for tag in annotation.tags %}

{%- if (tag.tag | lower == "problem") or (tag.tag | lower == "problems") %}

{%- set isMatch = true %}

{%- endif %}

{%- endfor %}

{%- if isMatch and annotation.annotatedText %}

<div style="color: {{ annotation.color | default('#ffd43b') }}; font-size: 1.15em; font-weight: 700; margin: 1em 0 0.15em 0;">Citation — {% if annotation.pageLabel %}Page {{ annotation.pageLabel }}{% else %}Annotation{% endif %}</div><span style="font-size: 1.05em; line-height: 1.65;">{{ annotation.annotatedText | safe }}</span><br>

{%- if annotation.tags and annotation.tags.length > 0 %}
{% for tag in annotation.tags %}#{{ tag.tag | replace(' ', '-') | lower }}{% if not loop.last %} {% endif %}{% endfor %}
{%- endif %}

{%- if annotation.comment %}

  

**Personal Note**

  

- {{ annotation.comment | safe }}

{%- endif %} 

{%- endif %}

{%- endfor %}

---
## 2. Constructs
- What concepts/variables does this paper define or measure?
	- Interaction cost
	- Cognitive effort
	- Attention residue
	- Task switching
	- Work fragmentation
	- Cognitive load
	- Task performance
	- Goal progress

{%- for annotation in annotations %}

{%- set isMatch = false %}

{%- for tag in annotation.tags %}

{%- if (tag.tag | lower == "constructs") or (tag.tag | lower == "construct") %}

{%- set isMatch = true %}

{%- endif %}

{%- endfor %}

{%- if isMatch and annotation.annotatedText %}
<div style="color: {{ annotation.color | default('#ffd43b') }}; font-size: 1.15em; font-weight: 700; margin: 1em 0 0.15em 0;">Citation — {% if annotation.pageLabel %}Page {{ annotation.pageLabel }}{% else %}Annotation{% endif %}</div><span style="font-size: 1.05em; line-height: 1.65;">{{ annotation.annotatedText | safe }}</span><br>
 


{%- if annotation.tags and annotation.tags.length > 0 %}
{% for tag in annotation.tags %}#{{ tag.tag | replace(' ', '-') | lower }}{% if not loop.last %} {% endif %}{% endfor %}
{%- endif %}

{%- if annotation.comment %}

  

**Personal Note**

  

- {{ annotation.comment | safe }}

{%- endif %}
  

{%- endif %}

{%- endfor %}

---

## 3. Theoretical Lens
- What theories, models, or conceptual frameworks does the paper use to explain why the phenomenon occur?
	- Distributed Cognition
	- Gulf of Execution
	- Goal Systems Theory
	- Action Identification Theory
	- Self-Determination Theory
	- Flow
	- Attention Residue
	- Cognitive Load Theory
	- Evolutionary Mismatch
 

{%- for annotation in annotations %}

{%- set isMatch = false %}

{%- for tag in annotation.tags %}

{%- if (tag.tag | lower == "theory") or (tag.tag | lower == "theoretical_lens") or (tag.tag | lower == "theories") %}

{%- set isMatch = true %}

{%- endif %}

{%- endfor %}

{%- if isMatch and annotation.annotatedText %}

<div style="color: {{ annotation.color | default('#ffd43b') }}; font-size: 1.15em; font-weight: 700; margin: 1em 0 0.15em 0;">Citation — {% if annotation.pageLabel %}Page {{ annotation.pageLabel }}{% else %}Annotation{% endif %}</div><span style="font-size: 1.05em; line-height: 1.65;">{{ annotation.annotatedText | safe }}</span><br>

{%- if annotation.tags and annotation.tags.length > 0 %}
{% for tag in annotation.tags %}#{{ tag.tag | replace(' ', '-') | lower }}{% if not loop.last %} {% endif %}{% endfor %}
{%- endif %}

{%- if annotation.comment %}

  

**Personal Note**

  

- {{ annotation.comment | safe }}

{%- endif %}
  

{%- endif %}

{%- endfor %}

  
---
## 4. Mechanism
- What causal process does the paper propose?
	- Application switching
	- affects
	- Context reconstruction
	- affects
	- Cognitive effort
	- affects
	- Interaction cost
	- affects
	- Reduced task performance

  

{%- for annotation in annotations %}

{%- set isMatch = false %}

{%- for tag in annotation.tags %}

{%- if (tag.tag | lower == "mechanic") or (tag.tag | lower == "mechanics") or (tag.tag | lower == "mechanism") %}

{%- set isMatch = true %}

{%- endif %}

{%- endfor %}

{%- if isMatch and annotation.annotatedText %}

<div style="color: {{ annotation.color | default('#ffd43b') }}; font-size: 1.15em; font-weight: 700; margin: 1em 0 0.15em 0;">Citation — {% if annotation.pageLabel %}Page {{ annotation.pageLabel }}{% else %}Annotation{% endif %}</div><span style="font-size: 1.05em; line-height: 1.65;">{{ annotation.annotatedText | safe }}</span><br>

{%- if annotation.tags and annotation.tags.length > 0 %}
{% for tag in annotation.tags %}#{{ tag.tag | replace(' ', '-') | lower }}{% if not loop.last %} {% endif %}{% endfor %}
{%- endif %}

{%- if annotation.comment %}

  

**Personal Note**

  

- {{ annotation.comment | safe }}

{%- endif %}

  
  

{%- endif %}

{%- endfor %}

  
---
## 5. Intervention
- What intervention, system, artefact, or implementation is studied?
	- Goal structures
	- Progress/state representation
	- Immediate feedback
	- Contextual information
	- Guided action
	- Persistent state
	- Visualisation
  

{%- for annotation in annotations %}

{%- set isMatch = false %}

{%- for tag in annotation.tags %}

{%- if (tag.tag | lower == "intervention") or (tag.tag | lower == "interventions") %}

{%- set isMatch = true %}

{%- endif %}

{%- endfor %}

{%- if isMatch and annotation.annotatedText %}

<div style="color: {{ annotation.color | default('#ffd43b') }}; font-size: 1.15em; font-weight: 700; margin: 1em 0 0.15em 0;">Citation — {% if annotation.pageLabel %}Page {{ annotation.pageLabel }}{% else %}Annotation{% endif %}</div><span style="font-size: 1.05em; line-height: 1.65;">{{ annotation.annotatedText | safe }}</span><br>

  



{%- if annotation.tags and annotation.tags.length > 0 %}
{% for tag in annotation.tags %}#{{ tag.tag | replace(' ', '-') | lower }}{% if not loop.last %} {% endif %}{% endfor %}
{%- endif %}

{%- if annotation.comment %}

  

**Personal Note**

  

- {{ annotation.comment | safe }}

{%- endif %}

    

{%- endif %}

{%- endfor %}



---
## 6. Context
- Population
- Context
- Industry
- Work environment
- Task
- Digital systems
- Country

{%- for annotation in annotations %}

{%- set isMatch = false %}

{%- for tag in annotation.tags %}

{%- if (tag.tag | lower == "context") %}

{%- set isMatch = true %}

{%- endif %}

{%- endfor %}

{%- if isMatch and annotation.annotatedText %}
<div style="color: {{ annotation.color | default('#ffd43b') }}; font-size: 1.15em; font-weight: 700; margin: 1em 0 0.15em 0;">Citation — {% if annotation.pageLabel %}Page {{ annotation.pageLabel }}{% else %}Annotation{% endif %}</div><span style="font-size: 1.05em; line-height: 1.65;">{{ annotation.annotatedText | safe }}</span><br>

{%- if annotation.tags and annotation.tags.length > 0 %}
{% for tag in annotation.tags %}#{{ tag.tag | replace(' ', '-') | lower }}{% if not loop.last %} {% endif %}{% endfor %}
{%- endif %}

{%- if annotation.comment %}

  

**Personal Note**

  

- {{ annotation.comment | safe }}

{%- endif %}


  

{%- endif %}

{%- endfor %}

---
## 7. Methodology
- **Study design**
    - **Intervention:** Experimental / quasi-experimental / observational
    - **Temporal:** Cross-sectional / longitudinal
    - **Setting:** Laboratory / field / online
    - **Approach:** Quantitative / qualitative / mixed-methods
    - **Data collection:** Experiment / survey / interview / observation / logs etc.
- **Sample**
    - Sample size:
    - Population:
    - Groups / conditions:
    - Attrition / exclusions:
- **Experimental structure**
    - Conditions:
    - Independent variables:
    - Dependent variables:
    - Control / comparison:
    - Duration:
  
{%- for annotation in annotations %}

{%- set isMatch = false %}

{%- for tag in annotation.tags %}

{%- if (tag.tag | lower == "method") or (tag.tag | lower == "methods")or (tag.tag | lower == "methodology") %}

{%- set isMatch = true %}

{%- endif %}

{%- endfor %}

{%- if isMatch and annotation.annotatedText %}

<div style="color: {{ annotation.color | default('#ffd43b') }}; font-size: 1.15em; font-weight: 700; margin: 1em 0 0.15em 0;">Citation — {% if annotation.pageLabel %}Page {{ annotation.pageLabel }}{% else %}Annotation{% endif %}</div><span style="font-size: 1.05em; line-height: 1.65;">{{ annotation.annotatedText | safe }}</span><br>

{%- if annotation.tags and annotation.tags.length > 0 %}
{% for tag in annotation.tags %}#{{ tag.tag | replace(' ', '-') | lower }}{% if not loop.last %} {% endif %}{% endfor %}
{%- endif %}

{%- if annotation.comment %}

  

**Personal Note**

  

- {{ annotation.comment | safe }}

{%- endif %}

  

{%- endif %}

{%- endfor %}


---
## 8. Measures
- What measures, metrics etc. were used
- Shows how other researchers operationalise constructs
- How should I measure x?

{%- for annotation in annotations %}

{%- set isMatch = false %}

{%- for tag in annotation.tags %}

{%- if (tag.tag | lower == "measure") or (tag.tag | lower == "measures") %}

{%- set isMatch = true %}

{%- endif %}

{%- endfor %}

{%- if isMatch and annotation.annotatedText %}

<div style="color: {{ annotation.color | default('#ffd43b') }}; font-size: 1.15em; font-weight: 700; margin: 1em 0 0.15em 0;">Citation — {% if annotation.pageLabel %}Page {{ annotation.pageLabel }}{% else %}Annotation{% endif %}</div><span style="font-size: 1.05em; line-height: 1.65;">{{ annotation.annotatedText | safe }}</span><br>

{%- if annotation.tags and annotation.tags.length > 0 %}
{% for tag in annotation.tags %}#{{ tag.tag | replace(' ', '-') | lower }}{% if not loop.last %} {% endif %}{% endfor %}
{%- endif %}

{%- if annotation.comment %}

  

**Personal Note**

  

- {{ annotation.comment | safe }}

{%- endif %}



  

{%- endif %}

{%- endfor %}

---
## 9. Results
- What mechanism produced what result?
  
{%- for annotation in annotations %}

{%- set isMatch = false %}

{%- for tag in annotation.tags %}

{%- if (tag.tag | lower == "result") or (tag.tag | lower == "results") %}

{%- set isMatch = true %}

{%- endif %}

{%- endfor %}

{%- if isMatch and annotation.annotatedText %}

<div style="color: {{ annotation.color | default('#ffd43b') }}; font-size: 1.15em; font-weight: 700; margin: 1em 0 0.15em 0;">Citation — {% if annotation.pageLabel %}Page {{ annotation.pageLabel }}{% else %}Annotation{% endif %}</div><span style="font-size: 1.05em; line-height: 1.65;">{{ annotation.annotatedText | safe }}</span><br>

{%- if annotation.tags and annotation.tags.length > 0 %}
{% for tag in annotation.tags %}#{{ tag.tag | replace(' ', '-') | lower }}{% if not loop.last %} {% endif %}{% endfor %}
{%- endif %}

{%- if annotation.comment %}

  

**Personal Note**

  

- {{ annotation.comment | safe }}

{%- endif %}

  

  

{%- endif %}

{%- endfor %}

  
---
## 10. Limitations & Quality
- Something not being reported is not the same and not performed. 
- Limitations Capture:
	- Sample
	- Ecological validity
	- Measurement validity
	- Confounds
	- Generalisability
	- Missing information
	- Author-report limitations
- Quality Capture:
	- Appropriate design?
	- Appropriate measures?
	- Appropriate analysis?
	- Validation?
	- Reproducibility?

{%- for annotation in annotations %}

{%- set isMatch = false %}

{%- for tag in annotation.tags %}

{%- if (tag.tag | lower == "limitations") or (tag.tag | lower == "limitation") or (tag.tag | lower == "quality") %}

{%- set isMatch = true %}

{%- endif %}

{%- endfor %}

{%- if isMatch and annotation.annotatedText %}

<div style="color: {{ annotation.color | default('#ffd43b') }}; font-size: 1.15em; font-weight: 700; margin: 1em 0 0.15em 0;">Citation — {% if annotation.pageLabel %}Page {{ annotation.pageLabel }}{% else %}Annotation{% endif %}</div><span style="font-size: 1.05em; line-height: 1.65;">{{ annotation.annotatedText | safe }}</span><br>

{%- if annotation.tags and annotation.tags.length > 0 %}
{% for tag in annotation.tags %}#{{ tag.tag | replace(' ', '-') | lower }}{% if not loop.last %} {% endif %}{% endfor %}
{%- endif %}

{%- if annotation.comment %}

  

**Personal Note**

  

- {{ annotation.comment | safe }}

{%- endif %}

  

  

{%- endif %}

{%- endfor %}

---
## 11. Relevance 
- How does this relate to my research?
- Which Research Question does this paper address?


{%- for annotation in annotations %}

{%- set isMatch = false %}

{%- for tag in annotation.tags %}

{%- if (tag.tag | lower == "relevance") or (tag.tag | lower == "relevant") %}

{%- set isMatch = true %}

{%- endif %}

{%- endfor %}

{%- if isMatch and annotation.annotatedText %}

<div style="color: {{ annotation.color | default('#ffd43b') }}; font-size: 1.15em; font-weight: 700; margin: 1em 0 0.15em 0;">Citation — {% if annotation.pageLabel %}Page {{ annotation.pageLabel }}{% else %}Annotation{% endif %}</div><span style="font-size: 1.05em; line-height: 1.65;">{{ annotation.annotatedText | safe }}</span><br>

  



{%- if annotation.tags and annotation.tags.length > 0 %}
{% for tag in annotation.tags %}#{{ tag.tag | replace(' ', '-') | lower }}{% if not loop.last %} {% endif %}{% endfor %}
{%- endif %}

{%- if annotation.comment %}

  

**Personal Note**

  

- {{ annotation.comment | safe }}

{%- endif %}

  



  

{%- endif %}

{%- endfor %}

  
---
---
# Additional Data

  

{% for annotation in annotations %}

{% if annotation.annotatedText %}

<div style="color: {{ annotation.color | default('#ffd43b') }}; font-size: 1.15em; font-weight: 700; margin: 1em 0 0.15em 0;">Citation — {% if annotation.pageLabel %}Page {{ annotation.pageLabel }}{% else %}Annotation{% endif %}</div><span style="font-size: 1.05em; line-height: 1.65;">{{ annotation.annotatedText | safe }}</span><br>

{%- if annotation.tags and annotation.tags.length > 0 %}
{% for tag in annotation.tags %}#{{ tag.tag | replace(' ', '-') | lower }}{% if not loop.last %} {% endif %}{% endfor %}
{%- endif %}

{%- if annotation.comment %}

  

**Personal Note**

  

- {{ annotation.comment | safe }}

{%- endif %}

  



  

{% endif %}

{% endfor %}

  

{% if notes and notes.length > 0 %}

---
## Zotero Notes

  

{% for note in notes %}

  

### Zotero Note

  

- {{ note.note | safe }}

  

{% endfor %}

  

{% endif %}

  
---
---
# Spaced Repetition

  

```button

name 🧠 Review Flashcards

type command

action Spaced Repetition: Review flashcards in this note

```


---
---