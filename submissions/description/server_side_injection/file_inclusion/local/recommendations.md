# Recommendations(s)

The most effective solution to eliminate file inclusion vulnerabilities is to avoid passing user-submitted input to any filesystem/framework API. If this is not possible the application can maintain an allow list of files, that may be included by the page, and then use an identifier (for example the index number) to access to the selected file. Any request containing an invalid identifier has to be rejected, in this way there is no attack surface for malicious users to manipulate the path.

For more information on secure file management, please refer to:
<https://cheatsheetseries.owasp.org/cheatsheets/File_Upload_Cheat_Sheet.html>
