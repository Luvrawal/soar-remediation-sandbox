### Recommended Remediation: DNS Security Misconfiguration

*(Note: DNS misconfigurations cannot be mitigated via webserver configuration. Update your authoritative DNS zone records as shown below.)*

#### SPF Record (TXT):
```text
v=spf1 include:_spf.example.com ~all
```

#### DMARC Record (_dmarc.example.com TXT):
```text
v=DMARC1; p=quarantine; rua=mailto:dmarc-reports@example.com; pct=100
```

#### DKIM Record (<selector>._domainkey.example.com TXT):
```text
v=DKIM1; k=rsa; p=<public-key>
```
