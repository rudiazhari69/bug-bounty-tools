# Bug Bounty Tools

A curated directory of well-known, public tools for bug bounty hunting — recon, interception, fuzzing, wordlists, exploitation helpers, and reporting. Every link goes to the tool's official project page or site.

> **Authorized testing only.** These tools are for targets you are allowed to test: a bug bounty program's in-scope assets, your own systems, or a lab. Never scan, probe, or exploit anything outside your authorization. Read the program's scope and rules first — every time.

## Start here (beginners)

If you are new, you do not need all 50 tools. Start with this chain:

1. **Read the scope** — know exactly which domains, apps, and vulnerability classes are in scope.
2. **Set up a proxy** — [Burp Suite Community](#proxies--interception) or [OWASP ZAP](#proxies--interception). Route your browser through it and learn to read requests.
3. **Enumerate subdomains** — [subfinder](#recon--enumeration) or [amass](#recon--enumeration).
4. **Find live hosts** — [httpx](#recon--enumeration).
5. **Crawl and harvest URLs** — [katana](#recon--enumeration), [gau](#recon--enumeration), [waybackurls](#recon--enumeration).
6. **Fuzz with wordlists** — [ffuf](#fuzzing--scanning) + [SecLists](#wordlists--content-discovery).
7. **Verify everything manually** before reporting — a scanner hit is a lead, not a finding.
8. **Write it up properly** — see [Reporting & notes](#reporting--notes), and the companion repo [bug-bounty-report-templates](https://github.com/rudiazhari69/bug-bounty-report-templates).

Most Go tools install with `go install <repo>@latest` — check each project's README for the exact command.

## Contents

- [Recon & enumeration](#recon--enumeration)
- [Proxies & interception](#proxies--interception)
- [Fuzzing & scanning](#fuzzing--scanning)
- [Wordlists & content discovery](#wordlists--content-discovery)
- [Exploitation helpers](#exploitation-helpers)
- [Reporting & notes](#reporting--notes)
- [Contributing](#contributing)

## Recon & enumeration

| Tool | What it does | Link |
| ---- | ------------ | ---- |
| subfinder | Fast passive subdomain discovery using public sources | [github.com/projectdiscovery/subfinder](https://github.com/projectdiscovery/subfinder) |
| amass | In-depth subdomain enumeration and network mapping (OWASP project) | [github.com/owasp-amass/amass](https://github.com/owasp-amass/amass) |
| dnsx | Fast, multi-purpose DNS toolkit: resolve, brute-force, wildcard checks | [github.com/projectdiscovery/dnsx](https://github.com/projectdiscovery/dnsx) |
| naabu | Fast port scanner with SYN/CONNECT support | [github.com/projectdiscovery/naabu](https://github.com/projectdiscovery/naabu) |
| httpx | Fast HTTP prober: finds live hosts and grabs titles, tech, and status codes | [github.com/projectdiscovery/httpx](https://github.com/projectdiscovery/httpx) |
| assetfinder | Finds subdomains and related domains for a target | [github.com/tomnomnom/assetfinder](https://github.com/tomnomnom/assetfinder) |
| findomain | Fast subdomain enumerator using multiple APIs and sources | [github.com/Findomain/Findomain](https://github.com/Findomain/Findomain) |
| gau | Fetches known URLs for a domain from OTX, Wayback, Common Crawl, and URLScan | [github.com/lc/gau](https://github.com/lc/gau) |
| waybackurls | Pulls archived URLs for a domain from the Wayback Machine | [github.com/tomnomnom/waybackurls](https://github.com/tomnomnom/waybackurls) |
| katana | Fast web crawler that maps endpoints, JS files, and forms | [github.com/projectdiscovery/katana](https://github.com/projectdiscovery/katana) |
| hakrawler | Simple, fast web crawler for discovering endpoints and JavaScript | [github.com/hakluke/hakrawler](https://github.com/hakluke/hakrawler) |
| subjack | Checks a list of subdomains for takeover vulnerabilities | [github.com/haccer/subjack](https://github.com/haccer/subjack) |
| crt.sh | Free Certificate Transparency search: find subdomains from issued certificates | [crt.sh](https://crt.sh) |
| Shodan | Search engine for internet-connected devices and services (account needed for full use) | [shodan.io](https://www.shodan.io) |
| Censys | Internet-wide scan data: find exposed hosts, certificates, and services | [censys.io](https://censys.io) |

## Proxies & interception

| Tool | What it does | Link |
| ---- | ------------ | ---- |
| Burp Suite | The standard intercepting proxy for manual web testing (Community free, Pro paid) | [portswigger.net/burp](https://portswigger.net/burp) |
| OWASP ZAP | Free, open-source intercepting proxy and scanner from OWASP | [zaproxy.org](https://www.zaproxy.org) |
| mitmproxy | Free, scriptable interactive HTTPS proxy (CLI, TUI, and web UI) | [github.com/mitmproxy/mitmproxy](https://github.com/mitmproxy/mitmproxy) |
| Caido | Lightweight, open-source web security auditing toolkit with a proxy | [github.com/caido/caido](https://github.com/caido/caido) |
| Proxify | Swiss-army proxy tool for capturing, manipulating, and replaying traffic | [github.com/projectdiscovery/proxify](https://github.com/projectdiscovery/proxify) |

## Fuzzing & scanning

| Tool | What it does | Link |
| ---- | ------------ | ---- |
| ffuf | Fast web fuzzer for directories, vhosts, parameters, and more | [github.com/ffuf/ffuf](https://github.com/ffuf/ffuf) |
| nuclei | Template-based vulnerability scanner with a huge community template library | [github.com/projectdiscovery/nuclei](https://github.com/projectdiscovery/nuclei) |
| gobuster | Fast directory, DNS, and vhost brute-forcer written in Go | [github.com/OJ/gobuster](https://github.com/OJ/gobuster) |
| dirsearch | Web path brute-forcer with built-in wordlists and extensions | [github.com/maurosoria/dirsearch](https://github.com/maurosoria/dirsearch) |
| wfuzz | Flexible web fuzzer for parameters, headers, paths, and auth | [github.com/xmendez/wfuzz](https://github.com/xmendez/wfuzz) |
| nikto | Classic web server scanner for known dangerous files and misconfigurations | [github.com/sullo/nikto](https://github.com/sullo/nikto) |
| whatweb | Fingerprints websites: CMS, frameworks, server, and plugins | [github.com/urbanadventurer/whatweb](https://github.com/urbanadventurer/whatweb) |
| wpscan | WordPress security scanner (themes, plugins, users, vulnerabilities) | [github.com/wpscanteam/wpscan](https://github.com/wpscanteam/wpscan) |
| dalfox | Fast XSS scanner and parameter analysis tool | [github.com/hahwul/dalfox](https://github.com/hahwul/dalfox) |
| Arjun | Discovers hidden HTTP parameters (GET, POST, JSON, XML) | [github.com/s0md3v/Arjun](https://github.com/s0md3v/Arjun) |
| ParamSpider | Mines parameters from archived URLs for a domain | [github.com/devanshbatham/ParamSpider](https://github.com/devanshbatham/ParamSpider) |

## Wordlists & content discovery

| Tool | What it does | Link |
| ---- | ------------ | ---- |
| SecLists | The standard collection of wordlists for discovery, fuzzing, and passwords | [github.com/danielmiessler/SecLists](https://github.com/danielmiessler/SecLists) |
| FuzzDB | Wordlists of attack payloads: XSS, SQLi, traversal, LFI, and more | [github.com/fuzzdb-project/fuzzdb](https://github.com/fuzzdb-project/fuzzdb) |
| PayloadsAllTheThings | Curated payloads and bypasses per vulnerability class | [github.com/swisskyrepo/PayloadsAllTheThings](https://github.com/swisskyrepo/PayloadsAllTheThings) |
| Assetnote Wordlists | Large, well-structured wordlists for content discovery | [github.com/assetnote/wordlists](https://github.com/assetnote/wordlists) |
| LinkFinder | Finds endpoints and parameters hidden inside JavaScript files | [github.com/GerbenJavado/LinkFinder](https://github.com/GerbenJavado/LinkFinder) |
| JSFinder | Extracts URLs, subdomains, and API paths from JS files | [github.com/Threezh1/JSFinder](https://github.com/Threezh1/JSFinder) |
| getJS | Quickly fetches all JS files for a domain (feeds LinkFinder / JSFinder) | [github.com/003random/getJS](https://github.com/003random/getJS) |
| subjs | Extracts subdomains and endpoints from JavaScript files | [github.com/lc/subjs](https://github.com/lc/subjs) |

## Exploitation helpers

> Authorized testing only — use these solely on targets you are explicitly allowed to test, and stop once you have enough proof for the report.

| Tool | What it does | Link |
| ---- | ------------ | ---- |
| sqlmap | Automatically tests for SQL injection flaws | [github.com/sqlmapproject/sqlmap](https://github.com/sqlmapproject/sqlmap) |
| XSStrike | Tests for cross-site scripting flaws, with payload generation | [github.com/s0md3v/XSStrike](https://github.com/s0md3v/XSStrike) |
| Commix | Command injection testing tool (find it on GitHub under commixproject) | — |
| jwt_tool | Inspects and tests JSON Web Tokens for common weaknesses | [github.com/ticarpi/jwt_tool](https://github.com/ticarpi/jwt_tool) |
| hashcat | Password auditing and recovery for authorized assessments | [github.com/hashcat/hashcat](https://github.com/hashcat/hashcat) |
| John the Ripper | Password auditing tool supporting many hash formats | [github.com/openwall/john](https://github.com/openwall/john) |

## Reporting & notes

| Tool | What it does | Link |
| ---- | ------------ | ---- |
| Obsidian | Local-first Markdown notes with linking; popular for hunt notes | [obsidian.md](https://obsidian.md) |
| Joplin | Free, open-source note-taking with sync and encryption | [joplinapp.org](https://joplinapp.org) |
| Dradis CE | Open-source collaboration and reporting for security assessments | [github.com/dradis/dradis-ce](https://github.com/dradis/dradis-ce) |
| Serpico | Report generation for penetration tests (findings to finished report) | [github.com/BuffaloWill/Serpico](https://github.com/BuffaloWill/Serpico) |
| CherryTree | Hierarchical note-taking app for structured findings | [github.com/giuspen/cherrytree](https://github.com/giuspen/cherrytree) |

## Contributing

Found a well-known tool that's missing, or a dead link? See [CONTRIBUTING.md](CONTRIBUTING.md).

## License

[MIT](LICENSE)
