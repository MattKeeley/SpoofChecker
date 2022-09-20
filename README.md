# spoofcheck

Original tool made by @BishopFox [spoofcheck](https://github.com/BishopFox/spoofcheck).

A program that checks if a domain (or list of domains) can be spoofed. The program checks SPF and DMARC records for weak configurations that allow spoofing. 

Additionally it will alert if the domain has DMARC configuration that sends mail or HTTP requests on failed SPF/DKIM emails.

Usage:

	./spoofcheck.py -d [DOMAIN]
	OR
	./spoofcheck.py -iL [DOMAIN_LIST]

Domains are spoofable if any of the following conditions are met:
- Lack of an SPF or DMARC record
- SPF record never specifies `~all` or `-all`
- DMARC policy is set to `p=none` or is nonexistent


## Dependencies
- `dnspython`
- `colorama`
- `py-emailprotections`
- `tldextract`

## Setup

Run `pip3 install -r requirements.txt` from the command line to install the required dependencies.
