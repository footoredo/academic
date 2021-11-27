## Publications / Preprints

{% for pub in site.data.publications %}
    {% if pub.accepted %}
        {% assign where = "" | split: "," %}
        {% assign where = where | push: pub.status.venue %}
        {% assign where = where | push: pub.status.year %}
        {% assign other = "" %}
        {% for item in pub.status %}
            {% if item[0] == "other" %}
                {% assign other = " " | append: item[1] %}
            {% elsif item[0] == "track" %}
                {% assign where = where | push: item[1] %}
            {% endif %}
        {% endfor %}
        {% assign where = where | join: " " %}
        {% assign status = "Accepted by **" | append: where | append: "**" | append: other %}
    {% else %}
        {% assign status = pub.status | capitablize %}
    {% endif %}
- {{ pub.authors | join: ", " }}. *"{{ pub.title }}"*. {{ pub.comment }}\\
🤜 {{ status }}. {% for link in pub.links %} [\[{{ link.name }}\]]({{ link.url }}) {% endfor %}
{% endfor %}