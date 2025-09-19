# Explore Google hacking and enumeration 

# AIM:

To use Google for gathering information and perform enumeration of targets

## STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various Google hacking keywords and enumeration tools as follows:


### Step 3:
Open terminal and try execute some kali linux commands

## Pen Test Tools Categories:  

| Operator    | Description                        | Example Usage           |
| ----------- | ---------------------------------- | ----------------------- |
| `site:`     | Search within a specific domain    | `site:example.com`      |
| `inurl:`    | Search in URL                      | `inurl:admin`           |
| `intitle:`  | Search in page title               | `intitle:"index of"`    |
| `filetype:` | Search by file type                | `filetype:pdf`          |
| `intext:`   | Search inside page text            | `intext:"confidential"` |
| `link:`     | Pages that link to a specific site | `link:example.com`      |
| `cache:`    | View cached version of a site      | `cache:example.com`     |
| `ext:`      | Same as filetype                   | `ext:xls`               |

 ## Architecture 
 ```
+----------------------+
|   Attacker / Hacker  |
|   (Browser & Google) |
+----------+-----------+
           |
           | Google Dork Queries
           v
+---------------------------+
|       Google Search       |
+---------------------------+
           |
           | Indexed Public Content
           v
+---------------------------+
|   Target Websites / Data  |
| - Leaked files            |
| - Open directories        |
| - Sensitive info          |
+---------------------------+

```

# Output:
<img width="1920" height="1080" alt="Screenshot (9)" src="https://github.com/user-attachments/assets/9bc39d74-9bcf-42fb-b319-6c85e2c55ad1" />
<img width="1920" height="1080" alt="Screenshot (10)" src="https://github.com/user-attachments/assets/d4bf0103-752a-4f7d-88c7-af931f67e19b" />
<img width="1920" height="1080" alt="Screenshot (11)" src="https://github.com/user-attachments/assets/1f4bc31c-5f02-4231-9fb0-917bac534a14" />
<img width="1920" height="1080" alt="Screenshot (12)" src="https://github.com/user-attachments/assets/c9fe9579-e74f-4990-8868-ccd2e248daa5" />
<img width="1920" height="1080" alt="Screenshot (13)" src="https://github.com/user-attachments/assets/3b6adae4-4bba-493e-81f3-af39be5e03d6" />
<img width="1920" height="1080" alt="Screenshot (14)" src="https://github.com/user-attachments/assets/56d3c99a-536c-40ac-a419-792cb8111479" />


# DNS Enumeration


## DNS Recon

| Record Type | Meaning                        | Example Output                   |
| ----------- | ------------------------------ | -------------------------------- |
| A           | Host to IPv4 address           | `example.com -> 93.184.216.34`   |
| AAAA        | Host to IPv6 address           | `example.com -> ::1`             |
| MX          | Mail server info               | `mail.example.com`               |
| NS          | Name servers                   | `ns1.example.com`                |
| TXT         | Misc data (SPF, verifications) | `v=spf1 include:_spf.google.com` |
| CNAME       | Canonical names (aliases)      | `www -> example.com`             |

## Common Tools Used (Kali Linux)

| Tool           | Description                                | Usage Example                           |
| -------------- | ------------------------------------------ | --------------------------------------- |
| `nslookup`     | DNS lookup tool (simple queries)           | `nslookup example.com`                  |
| `dig`          | DNS lookup utility (detailed)              | `dig example.com any`                   |
| `host`         | Simple DNS querying tool                   | `host example.com`                      |
| `dnsenum`      | Perl script to enumerate DNS info          | `dnsenum example.com`                   |
| `fierce`       | DNS scanner to locate non-contiguous IPs   | `fierce -dns example.com`               |
| `dnsrecon`     | Powerful DNS enumeration script            | `dnsrecon -d example.com -a`            |
| `theHarvester` | Subdomain enumeration using search engines | `theHarvester -d example.com -b google` |


## OUTPUT:

## Architecture Diagram 


## dnsenum
**Purpose:** A multithreaded Perl script to enumerate information from DNS servers.

**Use case:** Performs DNS zone transfers, brute force subdomains, and gather host IPs.

```
dnsenum example.com

```
## Output:
<img width="1920" height="935" alt="424816973-8d1c0edf-5c9e-412c-83dc-7fb9e261b2a6" src="https://github.com/user-attachments/assets/9d6ffedb-87ba-496a-90cf-6fb69313b8cc" />
<img width="1920" height="935" alt="424817020-43d22372-83eb-4c60-b998-c443aff97428" src="https://github.com/user-attachments/assets/c5d55f99-defa-45d5-bdee-890e40d20f4d" />
![424817095-be341bf6-d687-412b-b9d0-944119f91853](https://github.com/user-attachments/assets/336f5367-48bc-4fce-b622-5c54ff24bb49)



## smtp-user-enum
**Purpose:** Standalone tool used to enumerate valid users by using the VRFY, EXPN, or RCPT TO commands.

**Use case:** Brute-forces SMTP to find users.

```
smtp-user-enum -M VRFY -U users.txt -t <target-ip>
```
  
 ## Output
  


## nmap –script smtp-enum-users.nse <hostname>

**Purpose:** Uses smtp-enum-users NSE script to enumerate valid users on an SMTP server.

**Use case:** Helps identify email accounts on mail servers.

```
nmap -p 25 --script smtp-enum-users.nse <target-ip>
```
## OUTPUT:



## RESULT:
The Google hacking keywords and enumeration tools were identified and executed successfully
