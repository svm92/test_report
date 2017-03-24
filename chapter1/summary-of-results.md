## Summary of Results

The automated scan found a total of {{ book.n_of_vulnerabilities }} vulnerabilities. The following types of vulnerabilities were found:

{% for elem in book.vulnerabilities %}
{{elem}}
{% endfor %}


These vulnerabilities where found in the following URLs:

{% for elem in book.urls %}
{{elem}}
{% endfor %}
