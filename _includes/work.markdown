## Work Experiences

{% for work in site.data.work %}
- **{{ work.institute }}**  &nbsp; ( {{ work.start }} ➡️ {{ work.end }} )\\
*{{ work.position }}* {% for comment in work.comments %}
    - {{ comment }}{% endfor %}
{% endfor %}