# Attack Narrative

The scan consisted of a first stage of directory browsing (spidering){% if book.max_children > 0 %} for a maximum number of {{ book.max_children }} children directories{% endif %}. The second stage was an active scan that attempted to execute the following attacks in the target web application:
- Buffer Overflow
- CRLF Injection
- Cross Site Scripting (Persisting and Reflected)
- Format String Error
- Parameter Tempering
- Path Traversal
- Remote File Inclusion
- Remote OS Command Injection
- Server Side Code Injection
- Server Side Include
- SQL Injection
