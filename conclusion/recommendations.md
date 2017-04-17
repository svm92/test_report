# Recommendations

Given the vulnerabilities found, some possible recommendations to remediate each of them include:

{% for n in range(book.vulnerabilities|length) %}
####{{book.vulnerabilities[n]}}
{{book.solutions[n]}}
{% endfor %}
Contacting a professional penetration tester to solve these and many more issues is advised
