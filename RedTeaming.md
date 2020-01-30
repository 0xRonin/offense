# Red Teaming / Pentesting / Offense

Some notes on red teaming





## Example Objectives

- Test tools
	- A/V
	- EDR
	- Application Whitelisting
	- Firewall
	- IPS
	- IDS
	- WAF
	- SIEM
	- Alerts
- Test processes
	- Operations 	
	- SOC
	- Incident Response Plan
	- Server requests
	- Software installed
	- Permissions granted
	- Firewall rules applied vs what was requested
- Physical i.e. data center entry via tailgating





## Example Narratives
- Vulnerability scanning
- Attempted exploitation i.e. SQLmap or WPscan
- Phish
	- Credential harvester
	- Malicious attachment
- Link to malicious file
- Internet-facing service with vulnerability
- Lateral movement
- Password spraying i.e. ADFS or Skype
- Bruteforcing passwords i.e. ADFS or Skype
- Process auditing: Identify weaknesses or gaps in the processes that could cause security issues i.e. default firewall ports being opened despite not being requested
- Mailbox compromise
- Messenger compromise i.e. Skype or Slack
- Data exfiltration
- Social engineering i.e. via Skype or Phone
- Password reset request to helpdesk
- Payroll change request to HR rep
- Sending a colleague a malicious file via compromised Skype account
- 



## OpSec

AKA Operation Security. You need to have it and you have to want it! Or you're fooked!

- Do not use company infrastructure to access attacker infrastructure
  - TOR
  - Proxy
  - Home internet
- Practice deleting logs from your SIEM if possible
- Ensure that none of your emails, in particular message subjects, contain IoCs that could be found by others not in the know happening upon it
- Pad the beginning and end of malicious files where possible
- Change filenames of malicious files to something that goes along with the narrative where possible i.e. web shell changed from cmd.jsp to HrsBuild.jsp
- Modify hashes of publicly obtained malicious files
- Use a local firewall to isolate access to it to a malicious service if this cannot be done in advance by your infrastructure firewall
- Change hostname of attacker machine if it is something obvious i.e. "kali"
- Only allow what needs access to attacker infrastructure where possible in order to prevent services like Shodan or web proxies that visit new URLs from unintentionally revealing information.
- Make sure to fill out any forms necessary to perform pentesting in a CSP to reduce chances of them messing with infrastructure
- "Live off the land" as much as possible
- Drop as few files as possible; stay in memory as much as possible
- Consider uploading malicious files to VT/PT/Any.Run to determine if it would be detected by A/V. The hash can be changed so the version used in an attack is not easily found on VT. It could be found via YARA rule(s) after all.