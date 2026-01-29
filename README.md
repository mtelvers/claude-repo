# claude-repo

A test opam overlay repository for use with [braid](https://github.com/mtelvers/braid) merge-test.

## Packages

| Package | Description |
|---------|-------------|
| `braid.0.1.0` | Build status tracker for opam overlay repositories |
| `braid.dev` | Build status tracker for opam overlay repositories |
| `imapd.dev` | IMAP4rev2 server implemented in OCaml with EIO |
| `jpeg.dev` | Pure OCaml JPEG library |
| `ocaml-slurm.dev` | OCaml client library for Slurm REST API |
| `octopus_energy.dev` | OCaml library and CLI for Octopus Energy API |
| `smtpd.dev` | An SMTP server implemented in OCaml |

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
