## Summary of Results

The automated scan found a total of {{ book.n_of_vulnerabilities }} distinct vulnerabilities. The following types of vulnerabilities were found:

{% for n in range(book.vulnerabilities|length) %}
####{{book.vulnerabilities[n]}}
{{book.descriptions[n]}}
{% endfor %}
