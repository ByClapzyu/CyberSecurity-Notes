ejemplos de como llenar reportes #gemini : 


Filtro busquedas (SPLUNK)
- *| spath URL | search URL="https://m1crosoftsupport.co/login"
## Opción 1

****Time of activity:**** `02/20/2026 20:16:29.614`

****List of Affected Entities:**** h.harris@thetrydaily.thm   `personas afectadas`

****Reason for Classifying as True Positive:**** Clear phishing attempt. Email uses social engineering (urgency) and a suspicious sender domain (amazon.biz) to trick the user into clicking a shortened malicious URL

****Reason for Escalating the Alert:**** "Confirmed malicious email bypassed initial filters and reached the user's inbox. Immediate investigation required to determine if the user clicked the link.  

****Recommended Remediation Actions:****

- Delete the email from the user's inbox.
- Block the sender (`urgents@amazon.biz`) at the email gateway.
- Block the URL (`http://bit.ly/3sHkX3da12340`) at the proxy/firewall level.
****List of Attack Indicators:****
- ****Sender:**** `urgents@amazon.biz`
- ****URL:**** `http://bit.ly/3sHkX3da12340`
---------
