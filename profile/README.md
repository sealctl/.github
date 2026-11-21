<p>
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/sealctl/.github/main/brand/mark-dark.svg">
    <img src="https://raw.githubusercontent.com/sealctl/.github/main/brand/mark.svg" width="56" alt="sealctl">
  </picture>
</p>

### Your agents run the code. Your phone holds the keys.

sealctl keeps API keys, SSH keys and backup passwords off your disk. When an AI coding agent needs a key, your phone asks, you tap Allow, and the key goes into that one command. It never lands in a transcript, your shell history or a `.env` file. Every key comes from 24 words you write on paper, so a new phone or laptop gets everything back.

**Status:** in development. The current release, 0.5.0, keeps keys on a Ledger hardware wallet; the phone-approved version is being built here in the open.

| Repository | What's in it |
| --- | --- |
| [sealctl](https://github.com/sealctl/sealctl) | Command line tool, shared core and protocol (MIT) |
| [app](https://github.com/sealctl/app) | iPhone and Android app (AGPL-3.0) |
| [homebrew-tap](https://github.com/sealctl/homebrew-tap) | `brew install sealctl/tap/sealctl` |
| [website](https://github.com/sealctl/website) | [sealctl.com](https://sealctl.com) |

Found a security problem? Report it privately through [GitHub's security advisories](https://github.com/sealctl/sealctl/security/advisories/new), not in a public issue.
