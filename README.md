# web_hacking

<i><b><script>prompt("hack to learn")</script></b></i>

network diagnoses first
-- connection probls..
resolve.conf messed up due to overwrite issues
--> apt purge resolvconf && reboot

- first of all, try to automate words' spelling. Create bash profiles_
--> ~/bash.rc; ~/.profile ... whatever
--> alias <comandname> = "<commandsyntax"
--> source ~/<edited_profile_name>
  
  <b> Some small bash scripting notes as well</b>
  - if a word is on the directory or something: 
  -- if [ -d "word"] then echo "word is here"; 
  -- (condition not true [! -d "word"] then echo "word not"
  
Now, steps to think of before approaching a real target:
- recon script in sh for general view
- nikto for knowing what's in the url
- whatweb to find out tech and stuff
- dirb general folders present, dirsearch, gobuster, whatever
- check admin folders through custom script running through a file with default admin main folders
- copy entire website to local folder, options with wget, different approaches
- js files: hidden endpoints, comments, calls
- gotta love js files.. embrace them with: grep -Er 'href="[^\"]+"'; grep -Er '(http|https)://[^/"]+'; grep -Er 'hidden'; grep -Er '[0-9][0-9][0-9].[0-9][0-9][0-9].[0-9][0-9][0-9]'
- check forms in the entire website, which properties do they have (hidden; kind of action or where are they supposed to bring
submitted information to - :action /post <some_end_path>

- osinter script: social media, digital dumpsters, digital cemetery
- httprequests_list scripto on all the folders in the domain

--> "=" in some parameteter? Head it over right into the sqlmap inside lazyweb_

Search engines:
- Ask
- Base
- Bing
- DuckDuckGo
- Exalead
- Faroo
- Fastbot
- Google
- Mojeek
- Moose
- Search
- Tiger
- Wikipedia
- Yahoo
- Yandex



Attacks:
- XSS: reflected, stored and DOM-based
- SQLi, including blind
- CSRF
- Broken Access & Weak Management Sessions
- CRLF
- IDOR's
- HTTP parameter pollution
- Security Misconfiguration --> mostly leading to information disclosure situations
- OS & command execution
- Path traversal
- domain || subdomain takeover through dns dig records
- sensitive data online exposed: digital dumpster, osinter, digital cemetery

<b>More specific procedures</b>:
- add xss payload to see handling of double qutores or angle brackets
- test html5 attributes such as onload, onerror, etc, in elements like an img tag
- use and abuse csrf tokens and try to delete content both by GET and POST, see the answer from the server
- how is an account identifier treated or processed by the server? In the URL, is it passwd with a POST call? Try to modify it and access others
- does the site take a url parameter to load a resource? Try to change the value of that parameter.



Vectors for gathering some sort of information_
- Plugins
- HTML5 Canvas Image Extractionj
- Open TCP Port and Local Network Fingerprinting
- Invasive Authentication Mechanisms (NTLM and SPNEGO)
- USB Device ID Enumeration via the GamePad API
- Fonts
- Monitor, Widget and OS Desktop Resolution
- Display Media Information
- WebGL
- User agent and HTTP Headers
- Locale Fingerprinting
- Timezone and Clock Offset
- Javascript Performance Fingerprinting
- Keystroke Fingerprinting
- Operating System Type Fingerprinting

<b>Web apps general vulnerabilities</b>:
- misconfigurations
- default installations
- buffer overflows
- unpatched servers
- design flaws
- operation system flaws
- application flaws
- open services
- default passwords

<i>More technical stuff</i>
- Injection
- Broken authentication
- Sensitive Data Exposure
- XML enternal Entity
- Broken Access Control
- Security Misconfiguration
- XSS
- Insecure Deserialization
- Components with known vulns
- Insuficient Logging and monitoring


WAF's_

- Get to know cookies through GET requests (cookies are the new black).
- Make requests without user-agent.
- Requests to other open ports and grab the banners.
- Login page? Try ungenious and dummy payload like " or 1 = 1 --.
- Input fields like search bars, submissions, whatever, make some more noise <script>alert()</script>, invest more on prompt() or confirm().
- Put ../../../etc/passwd in a random parameter at the end of url or something. More common if the site is passing variable information
and stuff like that via GET and data is on the actual URL. Attach also ' OR SLEEP(5) OR '.
- GET requests with outdated protocols - HTTP/0.9 (for example) - or others older.
- Hping the application using FIN and RST and analyse response.
- Drop Action Technique - Send a raw crafted FIN/RST packet to server and identify response.

<b> OWASP check list </b>
  <i> Map the Application’s Content</i>
- Explore Visible Content
- Consult Public Resources
- Discover Hidden Content
- Discover Default Content
- Enumerate Identifier-Specified Functions
- Test for Debug Parameters
<i> Analyze the Application</i>
- Identify Functionality
- Identify Data Entry Points
- Identify the Technologies Used
- Map the Attack Surface
<i> Test Client-side Controls</i>
- Test Transmission of Data via the Client
- Test Client-side Control Over User Input
- Test Thick-client Components
<i>Test the Authentication Mechanism</i>
- Understand the Mechanism
- Test Password Quality
- Test for Username Enumeration
- Test Resilience to Password Guessing
- Test Any Account Recovery Function
- Test Any Remember Me Function
- Test Any Impersonation Function
- Test Username Uniqueness
- Test Predictability of Auto-Generated Credentials
- Check for Unsafe Transmission of Credentials
- Test for Logic Flaws
- Exploit Any Vulnerabilities to Gain Unauthorized Access
<i> Test the Session Management Mechanism</i>
- Understand the Mechanism
- Test Tokens for Meaning
- Test Tokens for Predictability
- Check for Insecure Transmission of Tokens
- Check for Disclosure of Tokens in Logs
- Check Mapping of Tokens to Sessions
- Test Session Termination
- Check for Session Fixation
- Check for XSRF
- Check Cookie Scope
<i> Test Access Controls</i>
- Understand the Access Control Requirements
- Testing with Multiple Accounts
- Testing with Limited Access
- Test for Insecure Access Control Methods
<i> Test for Input-Based Vulnerabilities</i>
- Fuzz All Request Parameters
- Test for SQL Injection
- Test for XSS and Other Response Injection
- Test for OS Command Injection
- Test for Path Traversal
- Test for Script Injection
- Test for File Inclusion
<i> Test for Function-Specific Input Vulnerabilities</i>
- Test for SMTP Injection
- Test for Native Software Vulnerabilities
- Test for SOAP Injection
- Test for LDAP Injection
- Test for XPath Injection
- Test for Script Injection
- Test for File Inclusion
<i> Test for Logic Flaws</i>
- Identify the Key Attack Surface
- Test Multistage Processes
- Test Handling of Incomplete Input
- Test Trust Boundaries
- Test Transaction Logic
<i> Test for Shared Hosting Vulnerabilities</i>
- Test Segregation in Shared Infrastructures
- Test Segregation between ASP-Hosted Applications
<i> Test for Web Server Vulnerabilities</i>
- Test for Default Credentials
- Test for Default Content
- Test for Dangerous HTTP Methods
- Test for Proxy Functionality
- Test for Virtual Hosting Misconfiguration
- Test for Web Server Software Bugs
<i> Miscellaneous Checks</i>
- Check for DOM-based Attacks
- Check for Frame Injection
- Check for Local Privacy Vulnerabilities
- Follow Up Any Information Leakage
- Check for Weak SSL Ciphers

the owasp testing methodology checklist (https://www.owasp.org/index.php/testing_checklist)

<i> Information Gathering</i>
- Spiders, Robots, and Crawlers
- Search Engine Discovery/Reconnaissance
- Identify application entry points
- Testing for Web Application Fingerprint
- Application Discovery
- Analysis of Error Codes
<i> Configuration Management Testing</i>
- SSL/TLS Testing (SSL Version, Algorithms, Key length, Digital Cert. Validity)
- DB Listener Testing
- Infrastructure Configuration Management Testing
- Application Configuration Management Testing
- Testing for File Extensions Handling
- Old, backup and unreferenced files
- Infrastructure and Application Admin Interfaces
- Testing for HTTP Methods and XST
<i> Authentication Testing</i>
- Credentials transport over an encrypted channel
- Testing for user enumeration
- Testing for Guessable (Dictionary) User Account
- Brute Force Testing
- Testing for bypassing authentication schema
- Testing for vulnerable remember password and pwd reset
- Testing for Logout and Browser Cache Management
- Testing for CAPTCHA
- Testing Multiple Factors Authentication
- Testing for Race Conditions
<i> Session Management</i>
- Testing for Session Management Schema
- Testing for Cookies attributes
- Testing for Session Fixation
- Testing for Exposed Session Variables
- Testing for CSRF
<i> Authorization Testing</i>
- Testing for Business Logic
<i> Business Logic Testing</i>
- Testing for Business Logic
<i> Data Validation Testing</i>
- Testing for Reflected Cross Site Scripting
- Testing for Stored Cross Site Scripting
- Testing for DOM based Cross Site Scripting
- Testing for Cross Site Flashing
- SQL Injection
- LDAP Injection
- ORM Injection
- XML Injection
- SSI Injection
- XPath Injection
- IMAP/SMTP Injection
- Code Injection
- OS Commanding
- Buffer overflow
- Incubated vulnerability
- Testing for HTTP Splitting/Smuggling
<i> Denial of Service Testing</i>
- Testing for SQL Wildcard Attacks
- Locking Customer Accounts
- Testing for DoS Buffer Overflows
- User Specified Object Allocation
- User Input as a Loop Counter
- Writing User Provided Data to Disk
- Failure to Release Resources
- Storing too Much Data in Session
- Web Services Testing
- WS Information Gathering
- Testing WSDL
- XML Structural Testing
- XML content-level Testing
- HTTP GET parameters/REST Testing
- Naughty SOAP attachments
- Replay Testing
<i> Web Services Testing</i>
- WS Information Gathering
- Testing WSDL
- XML Structural Testing
- XML content-level Testing
- HTTP GET parameters/REST Testing
- Naughty SOAP attachments
- Replay Testing
- Web Services Testing
- AJAX Vulnerabilities
- AJAX Testing
