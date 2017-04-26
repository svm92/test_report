# Attack Narrative

The scan was automatically executed with the help of OWASP ZAP {{ book.zap_version }}. The scan consisted of a first stage of directory browsing (spidering){% if book.max_children > 0 %} for a maximum number of {{ book.max_children }} children directories{% endif %}. The second stage was an active scan that attempted to execute the following attacks in the target web application:

|Attack|Description
|:---:|:---:|
|**Buffer Overflow**| In the case of a buffer overflow, the extra data might get written into a sensitive memory location. To check for this flaw, the program sends large strings of input text and checks for anomalous behavior.
|**Client Browser Cache**| Checks the headers of secure pages to ensure they don’t allow browsers to cache the page.
|**CRLF Injection**| CRLF refers to the Carriage Return and Line Feed special characters used to denote the end of a line. It might be abused by an attacker to split a HTTP response, which can lead to cross-site scripting or cache poisoning . The program tests for this vulnerability by trying to inject a new header into the response by sending a parameter preceded by CRLF characters.
|**Cross Site Scripting (Reflected)**| First, it submits a ‘safe’ value and checks the response for any instances of this value. Then, for any locations where this value was found in, the program attempts a series of attacks aimed at that location to confirm whether a XSS attack is possible.
|**Cross Site Scripting (Persistent)**| It begins by submitting a ‘safe’ value much like the reflected variant, but it then spiders the whole application to find any locations where the value might be found and tries to attack them. 
|**Directory Browsing**| Tries to gain access to a directory listing by examining the response for patterns commonly used with web server software such as Apache or IIS.
|**External Redirect**| Tries to force a redirect by sending specific parameter values to the URL, and then checks the headers and response to check whether a redirect occurred.
|**Format String Error**| Sends strings of input text that compiled C code would interpret as formatting parameters, and then looks for any anomalies.
|**Parameter Tempering**| Submits requests with parameter values known to cause errors, and compares the response against patterns found in common errors in Java, Microsoft VBScript, PHP and others.
|**Path Traversal**| Tries to access files and directories outside of the web document root using combinations of pathname prefixes and names of local files typically found in Windows or *NIX systems.
|**Remote File Inclusion**| Passes an external URL as a parameter value for the current URL and checks whether this causes the title of the page to change.
|**Remote OS Command Injection**| Submits *NIX and Windows OS commands as URL parameter values that would produce a specific output should the application be vulnerable. If this output isn’t found in the response, then it tries a more complex approach that involves blind injection by submitting sleep instructions and timing the responses.
|**Server Side Code Injection**| Submits PHP and ASP attack strings as URL parameter values and then examines the response.
|**Server Side Include**| Detects the OS the server is running on, and then sends a HTML SSI directive. The response is then analyzed to check whether it matches with a pattern indicating the SSI (Server Side Include) was successful.
|**SQL Injection**| Attacks URL parameters and form parameters with valid and invalid SQL syntax, using diverse SQL injection techniques such as error, Boolean or Union based injection.
