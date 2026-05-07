# Subdomain Finder

A simple Bash script to enumerate subdomains for a given domain using various reconnaissance tools.

## Features

- **TheHarvester**: Searches for subdomains using public sources.
- **DNSRecon AXFR**: Attempts zone transfer to find subdomains.
- **DNSRecon Brute Force**: Brute forces subdomains using a wordlist.
- **Subthreat**: Uses threat intelligence for subdomain discovery.

## Requirements

- Bash
- [theharvester](https://github.com/laramies/theHarvester)
- [dnsrecon](https://github.com/darkoperator/dnsrecon)
- [subthreat](https://github.com/hakluke/subthreat) (assuming this is the tool)
- [SecLists](https://github.com/danielmiessler/SecLists) (for wordlist)

Install dependencies:

```bash
# Install theharvester
pip install theharvester

# Install dnsrecon
pip install dnsrecon

# Install subthreat (if available via pip or clone repo)
# Assuming it's a Python tool
pip install subthreat

# Clone SecLists
git clone https://github.com/danielmiessler/SecLists /opt/SecLists
```

## Usage

```bash
chmod +x code
./code <domain> [<method>]
```

- `<domain>`: The target domain (e.g., example.com)
- `<method>`: Optional string of methods to use (default: "bzhs")
  - `b`: DNSRecon brute force
  - `z`: DNSRecon AXFR
  - `h`: TheHarvester
  - `s`: Subthreat

Example:

```bash
./code example.com
./code example.com bh
```

## Output

Results are saved to `/tmp/<domain>.txt`

## Troubleshooting

- Ensure all tools are installed and in PATH.
- For brute force, ensure SecLists is installed at `/opt/SecLists`.
- If zone transfer fails, it might not be allowed on the domain.
- Check permissions for writing to `/tmp/`.

## License

[Add license if applicable]