# Network-Traffic-Analysis
Digital Forensic Investigation and Network Traffic Analysis of a simulated cyberattack using Wireshark

Overview
This repository documents a digital forensic investigation of a packet capture (PCAP) file from a simulated cyberattack. The analysis focused on identifying malicious activities, extracting forensic evidence, and uncovering security misconfigurations using tools like Wireshark and NetworkMiner.

Objectives
Analyze network traffic for signs of malicious activity.
Extract forensic artifacts (e.g., IP addresses, credentials, file transfers).
Identify vulnerabilities and misconfigurations.
Answer forensic questions based on observed behavior.

Tools Used
Wireshark: For packet-level inspection and protocol stream analysis.
NetworkMiner: For session reconstruction and file extraction.
Steghide: Prepared for steganographic analysis (not used in this phase).
John the Ripper/Hashcat: Available for password hash cracking (not required).

Key Findings
Target IP: 192.168.X.X
Vulnerability: Unsecured FTP server allowing anonymous access on a deprecated Windows XP system.
Malicious Activity: Attacker uploaded `Pwdump7.exe`, `libeay32.dll`, and `hashlist.txt`, indicating potential credential harvesting.
HTTP Analysis: Flagged 404 responses for possible covert communication, pending further steganographic analysis.
Security Gaps: Lack of encryption, access controls, and monitoring.

Repository Contents
Report: Full forensic report in PDF format (Network Traffic Analysis Report.pdf`).
Screenshots: Visuals of Wireshark filters and outputs
Analysis_Notes: Detailed notes on investigation steps and observations.

Methodology
1. Loaded PCAP into Wireshark and analyzed protocol hierarchy.
2. Filtered FTP traffic (`ftp.request.command`) to examine login and file upload behaviors.
3. Identified target IP and service banner (Microsoft FTP Service on Windows XP).
4. Used `ftp.request.command == "STOR"` to analyze file uploads.
5. Inspected HTTP traffic (`http.response.code == 404`) for potential covert communication.

Recommendations
Disable anonymous FTP access and enforce strong authentication.
Upgrade legacy systems (e.g., replace Windows XP).
mplement secure protocols (FTPS/SFTP) for data transfers.
Conduct regular security audits and deploy intrusion detection systems.

How to Use
Review the report in `Report/` for a comprehensive analysis.
Explore screenshots in `Screenshots/` for visual insights.
Check `Analysis_Notes/` for detailed investigation steps.

Future Work
Perform steganographic analysis on HTTP 404 responses.
Conduct a broader network audit to identify additional vulnerabilities.
Validate security controls through penetration testing.

License
This project is licensed under the MIT License. See the `LICENSE` file for details.

Contact
Feel free to reach out via [https://www.linkedin.com/in/ebube-mbah-b44b29376?] or email [ebubemartin244@gmail.com] for Jobs or collaboration opportunities.
