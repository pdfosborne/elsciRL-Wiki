---
cite: {{citekey}} 
title: {{title}}
year: {{date | format ("YYYY")}}
tags: [{{allTags}}]
authors: {{authors}}
citations: {{extra}}
publisher: ArXiv
url: {{url}}
DOI: {{archiveID}}
type: {{itemType}}
---

# {{title}}

## Abstract 
{{abstractNote}}


---
## Notes
{% for annotation in annotations -%}{%- if annotation.annotatedText -%}{% if 'Red' in annotation.colorCategory %} 
##### {{annotation.annotatedText | escape }}{% else %}
<mark class="customZot-{% if annotation.color %}{{annotation.colorCategory}} {% endif %}">{{annotation.annotatedText | escape }}</mark>
{% endif %}{%- endif %} {% if annotation.imageRelativePath %} ![[{{annotation.imageRelativePath}}]]{% endif %}{% if annotation.comment %} 
>Annotation: {{annotation.comment}}
{% endif %}{% endfor -%}    
>


---
## Bibliography

```bibtex
{{bibliography}}
```
