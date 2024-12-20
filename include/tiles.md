{% macro link_tile_wall() -%}
<div class="link-tile-wall">
    {{ caller() }}
</div>
{%- endmacro %}

{% macro link_tile(title, description, link, img_src, color='purple') -%}
<a class="link-tile tile-{{ color }}" title="{{ description }}" href="{{ link }}">
    <div class="tile-content">
        <div class="tile-image">
        <img src="{{ img_src }}" alt="{{ title }}" />
        </div>
        <p>{{ title }}</p>
    </div>
</a>
{%- endmacro %}


{% macro contact_tile_wall() -%}
<script type="text/javascript">
    function reverse(s){ return s.split("").reverse().join(""); };
    function openMailer(element) {
        var e = element.getAttribute("href")
        var y = "mailto:" + reverse(e);
        element.setAttribute("href", y);
        element.setAttribute("onclick", "");
    };
</script>
<div class="contact-tile-wall">
    {{ caller() }}
</div>
{%- endmacro %}

{% macro contact_tile(name, function, email, link, color='green') -%}
{%- set ns = namespace(link_reversed='') -%}
{%- for str in link -%}
    {%- set ns.link_reversed = str ~ ns.link_reversed -%}
{%- endfor -%}
<a id="email" class="contact-tile tile-{{ color }}" href="{{ ns.link_reversed }}" onclick='openMailer(this);'>
    <div class="tile-content">
        <span>
        <p class="contact-tile-name">{{ name }}</p>
        <p class="contact-tile-function">{{ function }}</p>
        <p class="contact-tile-email">{{ email | replace('.', '<span style="display: none;">.bosch</span>.') }}</p>
        </span>
    </div>
</a>
{%- endmacro %}

{% macro contact_tile_image(img_src, text, link, color='green') -%}
{%- set ns = namespace(link_reversed='') -%}
{%- for str in link -%}
    {%- set ns.link_reversed = str ~ ns.link_reversed -%}
{%- endfor -%}
<a id="email" class="contact-image-tile" href="{{ ns.link_reversed }}" onclick='openMailer(this);'>
    <div class="tile-content">
        <img src="{{ img_src }}" alt="{{ text }}" />
    </div>
</a>
{%- endmacro %}


{% macro presentation_tile_wall() -%}
<div class="presentation-tile-wall">
    {{ caller() }}
</div>
{%- endmacro %}

{% macro presentation_tile(metadata, id, section, color='grey-green', image_url=None) -%}
{% set data = metadata[id] %}
<a class="presentation-tile tile-{{ color }}" href="/{{ section }}/{{ id }}">
    <div class="tile-content">
        <span>
        {% if data.image_url %}
        <img src={{ data.image_url }} alt="{{ data.topic }}" style="float:right; width:120px; height:auto;" />
        {% endif %}
        <h3>{{ data.topic }}</h3>
        <p><strong>{{ data.presenter }}</strong> | <strong>{{ data.affiliation }}</strong><br/>
        Time: <strong>{{ data.time }}</strong> &nbsp; Room: <strong>{{ data.room }}</strong></p>
        </span>
    </div>
</a>
{%- endmacro %}

{% macro presentation_time_tile(time, color='grey') -%}
<a class="presentation-time-tile tile-{{ color }}">
    <div class="tile-content">
        <h3>{{ time }}</h3>
    </div>
</a>
{%- endmacro %}


{% macro presentation_tile_overview(data, section) %}
{% call presentation_tile_wall() %}
  {% for key in data %}
    {{ presentation_tile(metadata=data, id=key, section=section) }}
  {% endfor %}
{% endcall %}
{%- endmacro %}


{% macro presentation_tile_timeslot_overview(data, section) %}
{% set ns = namespace(old_time='') %}
{% call presentation_tile_wall() %}
  {% for key, value in data.items() %}
    {% if ns.old_time != value.time %}
      {{ presentation_time_tile(value.time) }}
    {% endif %}
    {{ presentation_tile(metadata=data, id=key, section=section) }}
    {% set ns.old_time = value.time %}
  {% endfor %}
{% endcall %}
{%- endmacro %}