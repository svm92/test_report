## Summary of Results

The automated scan found a total of {{ book.n_of_vulnerabilities }} distinct vulnerabilities. The following types of vulnerabilities were found:

{% for n in range(book.vulnerabilities|length) %}
####{{book.vulnerabilities[n]}}
{{book.descriptions[n]}}  
This vulnerability was found in the following URL(s):  
{% for m in range(book.urls[n]|length) %}
{{book.urls[n][m]}}
{% endfor %}
{% endfor %}
