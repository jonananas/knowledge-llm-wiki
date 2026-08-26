# nabla-c0d3/SSLyze

Source URL: https://github.com/nabla-c0d3/sslyze
Primary source viewed: repository README and releases page
Latest release listed: 6.3.1
License: AGPL-3.0
Captured: 2026-08-26

SSLyze is a fast SSL/TLS scanning tool and Python library. The README says it analyzes a server's SSL/TLS configuration by connecting to it, checking encryption settings such as certificates, cipher suites, elliptic curves, and known TLS attacks.

## Main Points

- SSLyze is both a command-line tool and a Python library.
- It checks server-side SSL/TLS configuration by connecting to the target server.
- It evaluates certificates, cipher suites, elliptic curves, and related encryption settings.
- It checks for known TLS attacks including Heartbleed, ROBOT, and OpenSSL CCS injection.
- It is designed for speed and reliability, and the README says it is used to scan hundreds of thousands of servers every day.
- It can be run from CI/CD to continuously check servers against Mozilla's recommended TLS configurations.
- It has a documented Python API for embedding scans in Python applications, including serverless functions.
- It supports non-HTTP protocols including SMTP, XMPP, LDAP, POP, IMAP, RDP, Postgres, and FTP.
- Scan results can be saved to JSON for later processing.
- Installation is available via `pip install --upgrade sslyze`.
- The README also shows Docker usage and the repository includes a Dockerfile; for security-sensitive use, prefer auditing the Dockerfile and building a local image over blindly running a prebuilt image.
- By default, SSLyze checks scan results against Mozilla's "intermediate" TLS configuration and returns a non-zero exit code if the server is not compliant.
- The Mozilla profile can be changed with `--mozilla_config={old, intermediate, modern}`.
- Custom TLS configuration checks can be provided via `--custom_tls_config` using Mozilla's TLS configuration format.

## Example Commands

Install and scan:

```sh
pip install --upgrade pip setuptools wheel
pip install --upgrade sslyze
python -m sslyze www.yahoo.com www.google.com "[2607:f8b0:400a:807::2004]:443"
```

CI-style Mozilla profile check:

```sh
python -m sslyze --mozilla_config=modern mozilla.com
```

Custom policy check:

```sh
python -m sslyze --custom_tls_config custom_tls_config_example.json mozilla.com
```

Build a local container from the repository Dockerfile after review:

```sh
git clone https://github.com/nabla-c0d3/sslyze.git
cd sslyze
docker build -t local/sslyze .
docker run --rm -it local/sslyze www.example.com
```

Use TLS scans only on systems you own or have permission to assess.

## Notable Links From The Repo

- Repository: https://github.com/nabla-c0d3/sslyze
- Python API documentation: https://nabla-c0d3.github.io/sslyze/documentation/
- Releases: https://github.com/nabla-c0d3/sslyze/releases
- Mozilla TLS configuration generator: https://ssl-config.mozilla.org/
- Mozilla server-side TLS recommendations: https://wiki.mozilla.org/Security/Server_Side_TLS
