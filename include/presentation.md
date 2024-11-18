{% macro overview(metadata) -%}

# {{ metadata.topic }}

<img src="{{ metadata.image }}" style="float:right; width:140px; height:auto;"/>

By <strong>{{ metadata.presenter }}</strong> of <strong>{{metadata.affiliation }}</strong>  
Time: <strong>{{ metadata.time }}</strong>&nbsp;Room: <strong>{{ metadata.room }}</strong>

{% if metadata.description -%}
## Description

{{ metadata.description }}

{% endif %}

{% if metadata.abstract -%}
## Abstract

{{ metadata.abstract }}

{% endif %}

{% if metadata.biography -%}
## Biography

{{ metadata.biography }}

{% endif %}

{% if metadata.slides -%}
## Slides

[Download slides]({{ metadata.slides }}){ .md-button .md-button--primary }

{% endif %}

{% if metadata.recording -%}
## Recording

[watch recording]({{ metadata.recording }}){ .md-button .md-button--primary }

{% endif %}

{% endmacro %}
