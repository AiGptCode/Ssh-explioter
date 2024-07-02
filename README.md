# ssh_exploiter CVE-2024-6387 with auto ip scanner and auto expliot 

 
# OpenSSH Vulnerability Checker & Exploiter

This Python script checks if servers are running vulnerable versions of OpenSSH and attempts exploitation if possible.

## Features

- **SSH Version Detection**: Retrieves SSH banner to determine the OpenSSH version.
- **Vulnerability Check**: Verifies if the detected version is vulnerable based on known vulnerable versions.
- **Exploitation Attempt**: Tries to exploit race condition vulnerability on vulnerable servers.
- **Multithreaded Scanning**: Utilizes threading for concurrent vulnerability checks on multiple targets.

## Requirements

- Python 3.x
- Required Python packages (install via `pip install -r requirements.txt`):
  - `ipaddress`
  
## Usage

```bash
python3 ssh_exploit.py <targets> [--port PORT] [-t TIMEOUT] [-l IP_LIST_FILE]
```

- **targets**: IP addresses, domain names, file paths containing IP addresses, or CIDR network ranges to scan.
- `--port PORT`: Port number to check (default: 22).
- `-t TIMEOUT`: Connection timeout in seconds (default: 1 second).
- `-l IP_LIST_FILE`: File containing a list of IP addresses to check.

## Example

```bash
python3 ssh_exploit.py 192.168.1.1 10.0.0.0/24 --port 22 -t 1.5
```

## Output

Upon completion, the script outputs a summary of the scan:

- **Servers not vulnerable**: Lists servers that are not running vulnerable versions.
- **Servers likely vulnerable**: Lists servers that are potentially vulnerable based on detected OpenSSH version.
- **Servers with port closed**: Displays the number of servers where the specified port is closed.
- **Total scanned targets**: Shows the total number of targets scanned.

## Notes

- Ensure you have appropriate permissions before scanning servers.
- Use responsibly and only on systems you are authorized to test.
