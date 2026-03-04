# SOC Lab 02 — Network Path Analysis

## Objective
Use common network diagnostic tools to:
- Measure latency to multiple hosts
- Identify network path hops
- Observe differences in routing to global endpoints
- Compare IPv4 vs IPv6 behavior (optional)

This lab introduces packet flow fundamentals used in troubleshooting, networking, and cybersecurity operations.

---

## Lab Time
~10–15 minutes

---

## Requirements
- Windows, Linux, or macOS terminal
- Internet connection

---

## Tools
- `ping`
- `traceroute` (Linux/macOS) or `tracert` (Windows)
- Optional: `mtr` (Linux)

---

## Step 1 — Basic Ping Tests

Run ping to three different hosts:

### Example hosts
- `google.com`
- `cloudflare.com`
- `openai.com`

### Commands

#### Windows:
```powershell
ping google.com
ping cloudflare.com
ping openai.com
```

#### Linux/macOS:
```bash
ping -c 4 google.com
ping -c 4 cloudflare.com
ping -c 4 openai.com
```

### Deliverables
Record the following for each host:
- Average latency (ms)
- Packet loss (should be 0%)
- IP address resolved

---

## Step 2 — Run Traceroute / Tracert

### Windows:
```powershell
tracert google.com
```

### Linux/macOS:
```bash
traceroute google.com
```

Repeat for:
- `cloudflare.com`
- `openai.com`

### Deliverables
For each trace:
- Number of hops  
- The first hop (your router)  
- Any `* * *` hops (timeouts)  
- Final destination IP  

---

## Step 3 — Compare Routing Differences

Answer these questions:

1. Which destination had the **fewest hops**?  
2. Which had the **highest latency**?  
3. Did all three take **different network paths** or did some share common early hops?  
4. Did any hops belong to major ISPs or backbone networks?

Write 3–5 sentences summarizing your observations.

---

## Optional Step (Linux Only) — Use MTR
If installed:
```bash
mtr google.com
```

This combines ping + traceroute in one tool.

---

## Reflection Questions
1. Why is traceroute useful for troubleshooting?  
2. Why do some hops not respond (`* * *`)?  
3. What does latency tell you about network congestion or distance?  
4. Can different DNS resolvers affect the path taken?  

---

## Cleanup
No cleanup needed.
---
## Screenshots

### Ping Test
![Ping Results](screenshots/Screenshot%20%2810%29.png)

### Traceroute to Google
![Traceroute Google](screenshots/Screenshot%20%2811%29.png)

### Traceroute to Cloudflare
![Traceroute Cloudflare](screenshots/Screenshot%20%2812%29.png)

---

## Next Steps
To continue building network investigation skills:

- **SOC Lab 03 — DNS Resolution & Caching**
- Examine how domain names are resolved into IP addresses
- Compare responses across different DNS resolvers
- Observe caching behavior and TTL values in DNS queries

Understanding DNS behavior is critical for detecting malicious domains and command-and-control activity.
