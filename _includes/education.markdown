## Education

{% for education in site.data.education %}
- **{{ education.institute }}**  &nbsp; ( {{ education.start }} ➡️ {{ education.end }} )\\
*{{ education.position }}* in {{education.subject}} {% for comment in education.comments %}
    - {{ comment }}{% endfor %}
{% endfor %}