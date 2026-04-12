# Homebrew Tap for Bravros CLI

This tap serves **only the CLI binary** (`bravros`). No skills, hooks, templates, or configuration files are distributed through Homebrew. All skill content is fetched securely by the CLI after activation.

## Installation

```sh
brew install bravros/tap/bravros
```

## Activation

After installing the binary, run:

```sh
bravros activate <license-key>
```

This installs skills, hooks, and configures Claude Code against the authenticated API at `app.bravros.dev`. Visit [bravros.dev](https://bravros.dev) to obtain your license key.

## Signature Verification

The formula includes a `verify do` block that runs `minisign -Vm` against the bundled `checksums.txt.minisig` using the pinned public key. You can confirm this pinned key matches the canonical key published at [bravros.dev/security](https://bravros.dev/security).

## What this tap does NOT contain

- `skills/` — delivered by the CLI after `bravros activate`
- `templates/` — delivered by the CLI after `bravros activate`
- `hooks.json` — written by the CLI after `bravros activate`
- `config/settings.json` — written by the CLI after `bravros activate`

All of the above are fetched from the authenticated distribution API, never from Homebrew.
