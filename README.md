# Using-Wireshark---analyzing-web-browser-artifacts-email-header-analysis
## AIM:
To use Wireshark to analyze web browser activities and inspect email headers from captured network traffic.
## Architecture Diagram:
```mermaid
flowchart TD
    A[User System] --> B[Web Browser]
    A --> C[Email Client]
    B --> D[Network Traffic]
    C --> D
    D --> E[Wireshark Capture Engine]
    E --> F[Protocol Decoders HTTP SMTP IMAP POP]
    F --> G[Browser Artifacts URLs Cookies Auth]
    F --> H[Email Headers Source IP Server Timestamps]
    G --> I[Findings and Reports]
    H --> I
```
## DESIGN STEPS:
### Step 1:
- Install Wireshark and ensure correct network adapter selection.
- Enable packet capturing for your active interface (Wi-Fi/Ethernet).

### Step 2:
**Web Browser Artifact Analysis**
- Open a browser and visit websites with login forms (use dummy credentials).
- In Wireshark, filter traffic with:
    - ```http``` for normal HTTP requests
    - ```http.cookie``` for cookies
    - ```http.authbasic``` for basic authentication
- Identify:
    - URLs visited
    - GET/POST requests
    - Cookies & session IDs
    - Credentials (if plaintext HTTP is used)
### Step 3:
- Capture email traffic by sending/receiving emails (dummy mail server or provided PCAP).
- Use filters:
    - ```smtp``` (Simple Mail Transfer Protocol)
    - ```pop``` / ```imap``` (for received mail)
- Inspect email headers:
    - Source IP
    - Mail server hostname
    - Timestamps
    - Possible forged headers
## PROGRAM:
```mermaid
flowchart TD
    A[Start Wireshark Capture] --> B[Generate Traffic: Web Browsing & Emails]
    B --> C[Apply Protocol Filters: HTTP/SMTP/IMAP/POP]
    C --> D[Extract Browser Artifacts: URLs, Cookies, Credentials]
    C --> E[Analyze Email Headers: Source, Server, Metadata]
    D --> F[Save Findings]
    E --> F[Save Findings]
    F --> G[Generate Digital Forensic Report]
```

## OUTPUT:
Captured Web Activity and Email Header Information

## GMAIL IN BROWSER
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/7127d4cf-ea65-4fa3-8360-22c15094128e" />

## SENDING AN EMAIL
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/d11d7d1b-14e8-45f7-bbab-77188015abea" />

## FILTER FOR DNS
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/334dff22-8787-48a6-9e1c-677719200488" />

## FILTER FOR HTTP
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/c9c1284d-7a7a-48ba-a540-2cd627e1f87d" />

## FILTER FOR TCP PORT 443
<img width="1920" height="1080" alt="Image" src="https://github.com/user-attachments/assets/160f4a23-59cc-48c2-8fc8-8ffd3a791afb" />


## RESULT:
Web browser artifacts and email headers were successfully analyzed using Wireshark.

