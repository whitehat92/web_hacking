# web_hacking

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
