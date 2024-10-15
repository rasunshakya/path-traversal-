 This project demonstrates a simple website with a vulnerable search function that is susceptible to a path traversal attack. The website allows users to search and retrieve files from the server. However, due to improper input validation, an attacker can manipulate the search input to traverse directories and access files outside the intended search scope.

The repository contains an HTML frontend, PHP backend, and example files that showcase how the path traversal attack can be exploited.

Features:

Vulnerable search form
Unvalidated file retrieval
Demonstrates path traversal vulnerability (CWE-22)
Vulnerability Details:
The vulnerability exists in the search function that retrieves files from the server based on user input. Due to the lack of proper sanitization of the search input, an attacker can manipulate the input to include special characters like ../, which allows directory traversal outside the intended folder.

This can lead to unauthorized access to sensitive files on the server, such as configuration files, user data, or other protected resources.

Steps to Exploit the Vulnerability:
Access the Search Function:

Open the web application in your browser.
Navigate to the Search page (e.g., http://localhost/vulnerable-search/index.html).
Normal Search:

Enter a file name in the search box (e.g., example.txt).
Click the Search button.
The server will retrieve and display the contents of the example.txt file.
Exploit the Path Traversal Vulnerability:

Instead of a normal file name, input a path traversal payload such as:
../../secret.txt (depending on the directory structure of the server).
Click the Search button.
The server will improperly process the request, allowing you to access the contents of the secret.txt file, which is stored outside the intended search directory.
Success Confirmation:

Upon successful exploitation, you will see the contents of secret.txt displayed, confirming the vulnerability.
