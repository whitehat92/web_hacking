# web_hacking

network diagnoses first
-- connection probls..
resolve.conf messed up due to overwrite issues
--> apt purge resolvconf && reboot

- first of all, try to automate words' spelling. Create bash profiles_
--> ~/bash.rc; ~/.profile ... whatever
--> alias <comandname> = "<commandsyntax"
--> source ~/<edited_profile_name>
  
Now, steps to think of before approaching a real target:
- recon script in sh for general view
- nikto for knowing what's in the url
- whatweb for what technologies are there
- dirb general folders present
- script for checking admin folders, the one in python
- copy website to local folder
- check js files, what url's are there:
just:
- grep -Eo 'href="[^\"]+"'  
- grep -Eo '(http|https)://[^/"]+'
- check the forms, is there any hidden value on them
- osinter script to find out information online
- put httprequests_list script running for all the folders in the domain
- sqlmap if a parameter retrieves information with "="

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

More specific procedures:_
- add xss payload to see handling of double qutores or angle brackets
- test html5 attributes such as onload, onerror, etc, in elements like an img tag
- use and abuse csrf tokens and try to delete content both by GET and POST, see the answer from the server
- how is an account identifier treated or processed by the server? In the URL, is it passwd with a POST call? Try to modify it and access others
- does the site take a url parameter to load a resource? Try to change the value of that parameter.

WAF's_

- Make a normal GET request from a browser, intercept and record response headers (specifically cookies).
- Make a request from command line (eg. cURL), and test response content and headers (no user-agent included).
- Make GET requests to random open ports and grab banners which might expose the WAFs identity.
- If there is a login page somewhere, try some common (easily detectable) payloads like " or 1 = 1 --.
- If there is some input field somewhere, try with noisy payloads like <script>alert()</script>.
- Attach a dummy ../../../etc/passwd to a random parameter at end of URL.
- Append some catchy keywords like ' OR SLEEP(5) OR ' at end of URLs to any random parameter.
- Make GET requests with outdated protocols like HTTP/0.9 (HTTP/0.9 does not support POST type queries).
- Many a times, the WAF varies the Server header upon different types of interactions.
- Drop Action Technique - Send a raw crafted FIN/RST packet to server and identify response.
