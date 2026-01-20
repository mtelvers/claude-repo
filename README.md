# claude-repo

A test opam overlay repository for use with [braid](https://github.com/mtelvers/braid) merge-test.

## Packages

| Package | Description |
|---------|-------------|
| `braid.dev` | Build status tracker for opam overlay repositories |
| `imapd.dev` | IMAP4rev2 server (RFC 9051) with EIO and PAM authentication |
| `smtpd.dev` | SMTP server (RFC 5321) with STARTTLS, DKIM, SPF, DMARC support |

## Usage

Test this overlay with braid:

```bash
# Quick dependency check
braid merge-test /path/to/claude-repo --dry-run -o results

# Full build test
braid merge-test /path/to/claude-repo -o results

# Stack with another overlay (claude-repo has higher priority)
braid merge-test /path/to/claude-repo /path/to/other-overlay -o results
```

## Repository Structure

```
claude-repo/
├── repo                              # opam repository metadata
└── packages/
    ├── braid/braid.dev/opam
    ├── imapd/imapd.dev/opam
    └── smtpd/smtpd.dev/opam
```

## Adding as an opam Repository

```bash
opam repository add claude-repo https://github.com/mtelvers/claude-repo.git
```

## License

ISC
