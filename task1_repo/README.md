# Task 1 - Network Port Scanning (Cyber Security Internship)

## Objective:
Perform a local network scan using Nmap to discover open ports and identify potential security risks.

---

## Tools Used:
- [Nmap](https://nmap.org/)
- Wireshark (optional)

---

## Commands Used:

```bash
nmap -sS 192.168.1.0/24
```

- `-sS`: TCP SYN scan (stealthy and commonly used)
- `192.168.1.0/24`: Scans all 254 IPs in this private subnet

---

## Observed Open Ports:

| Port | Service        | Description            |
|------|----------------|------------------------|
| 135  | msrpc          | Microsoft RPC          |
| 139  | netbios-ssn    | NetBIOS Session Service|
| 445  | microsoft-ds   | SMB over TCP           |
| 1521 | oracle         | Oracle Database        |
| 3306 | mysql          | MySQL Database         |
| 6646 | unknown        | Unknown (Investigating)|

---

## Analysis:

### Known Services:
- **135, 139, 445**: Windows networking services — potential risk if exposed externally.
- **1521, 3306**: Database ports — should be firewalled or limited to specific IPs.

### Unknown Port (6646):
This port is open but not identified by default Nmap scan.
- Could be a custom application.
- Requires manual investigation.

---

## Potential Security Risks:
- Exposed database ports can be brute-forced.
- Windows RPC/SMB are commonly targeted by malware.
- Unknown open ports can be exploited if unmonitored.

---

## Recommendations:
- Use a **firewall** to restrict unnecessary open ports.
- Ensure **strong authentication** on database services.
- Investigate unknown open ports (like `6646`).
- Run regular scans to monitor for unexpected services.

---

## Optional:
Packet capture was also analyzed with Wireshark to correlate port usage.

---

## Author:
[Your Name]

---

## Submission:
[GitHub Repo Link Here]
