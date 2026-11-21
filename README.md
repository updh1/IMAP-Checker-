IMAP Checker v2.0 — IMAP Credential Verifier
A high-throughput, multi-threaded IMAP credential checker with a live terminal dashboard. Feed it a combo list (email:password), pick a thread count, and it verifies each account against the correct provider's IMAP server in real time.

Resolves the right IMAP host per email domain using a built-in registry of 640+ providers (Gmail, Outlook/Hotmail/Live, Yahoo, AOL, iCloud, Yandex, Mail.ru, Zoho, GMX, Fastmail, Proton-style, ISP mail, regional providers, etc.). Unknown domains fall back to imap.<domain> then mail.<domain>.
Authenticates over IMAP (SSL or STARTTLS) with a configurable timeout and a thread pool (1–500 workers, default 25).

## Classifies every result into one of four buckets:
```bash
VALID — login succeeded
INVALID — auth rejected (wrong password, locked, disabled, …)
BLOCKED — rate-limited / captcha / IP throttled
ERROR — network, DNS, TLS, timeout
```
Streams a live dashboard (Rich) with running stats, progress bar, ETA, rate/s, and a color-coded live log.

## Writes results as it goes — no data lost on Ctrl+C:
```bash
results/valid_<ts>.txt — valid hits only (email:password)
results/results_<ts>.csv — every result with status, host, elapsed ms, reason
results/results_<ts>.json — full dump written on exit
```
Optional proxy support — HTTP/HTTPS/SOCKS4/SOCKS5 with auth, round-robin pool. Used transparently per attempt via raw socket CONNECT.


## Disclaimer
```bash
Use only against accounts you are authorized to test. Running this against third-party accounts without consent is illegal in most jurisdictions and violates every provider's ToS. The author assumes no liability for misuse.
```
