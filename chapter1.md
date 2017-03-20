# Executive Summary

The purpose of this automated test was to confirm whether the target web application meets the most basic security requirements. The test was meant to simulate a malicious attacker exploiting common vulnerabilities and breaches in a web application. The attacks were conducted under the level of access and privilege that a general Internet user would have.


Vulnerabilities found:
{% for elem in book.vulnerabilities %}
{{elem}}
{% endfor %}

Severity of vulnerabilities found:  
Low risk: {{ book.n_of_low_risks }}  
Medium risk: {{ book.n_of_medium_risks }}  
High risk: {{ book.n_of_high_risks }}

Affected URLs:
{% for elem in book.urls %}
{{elem}}
{% endfor %}

A total of {{ book.n_of_vulnerabilities }} vulnerabilities were found.
