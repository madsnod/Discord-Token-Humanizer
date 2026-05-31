# Discord Account Humanizer

A high-performance, multi-threaded Discord account humanizer that bulk-updates account profiles with random display names, bios, pronouns, avatars, and HypeSquad houses — all with proxy rotation support.

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.10+-blue?style=flat-square" />
  <img src="https://img.shields.io/badge/Status-Working-brightgreen?style=flat-square" />
</p>

---

## Features

- **Rust-Powered HTTP** — Uses `primp` for blazing-fast API requests
- **Multi-Threaded** — Process hundreds of accounts concurrently
- **Proxy Rotation** — Automatic proxy cycling with bad proxy detection & removal
- **Retry Logic** — Intelligent retries on transient errors and proxy failures
- **Avatar Optimization** — Auto-resizes and compresses images to fit Discord's 1MB limit
- **HypeSquad Assignment** — Randomly assigns a HypeSquad house to each account
- **Real-Time Logging** — Neon-themed console output with per-token status tracking
- **Configurable** — Toggle each feature on/off via `config.json`

---

## Tutorial

### 1. Install Dependencies

Make sure you have **Python 3.10 or higher**.


### 2. Fill Your Files

All folders and files come pre-filled and ready to go. You only need to add your **tokens** to `input/tokens.txt` — everything else works out of the box.

If you want, you can also customize:
- **`input/proxies.txt`** — Add proxies (supports `ip:port`, `user:pass@ip:port`, `http://`, `socks5://`). Optional — runs without proxies if empty.
- **`data/names.txt`** — Add more display names to pick from
- **`data/bios.txt`** — Add more bios to pick from
- **`data/pronouns.txt`** — Add more pronoun sets (e.g. `he/him`, `she/her`, `they/them`)
- **`avatar/`** — Add more avatar images (auto-resized to 256×256 and compressed)
- **`banners/`** — Add profile banner images (Nitro accounts only)

### 3. Configure (Optional)

Edit `config.json` to customize behavior:

| Option | Default | Description |
|---|---|---|
| `max_threads` | `3` | Number of concurrent threads |
| `avatar_dimension` | `256` | Avatar resize dimension (px) |
| `max_avatar_cache` | `100` | Max avatars cached in memory |
| `update_display_name` | `true` | Toggle display name updates |
| `update_bio` | `true` | Toggle bio updates |
| `update_pronouns` | `true` | Toggle pronoun updates |
| `update_avatar` | `true` | Toggle avatar updates |
| `update_hypesquad` | `true` | Toggle HypeSquad assignment |
| `RetryLimit` | `1` | Max retries per failed operation |

### 4. Run

```bash
Humanizer.exe
```

You'll be prompted for the thread count (or just press Enter for the default). The script will process all tokens and output a summary with success/failure stats.

---


## Output Files

After running, two files are generated inside `input/`:

- **`success.txt`** — Tokens that were successfully processed
- **`failed.txt`** — Tokens that failed (with reason)

---

## Disclaimer

This project is provided for **educational purposes only**. The use of this tool may violate Discord's Terms of Service. I am **not responsible** for any consequences resulting from the use of this software, including but not limited to account suspensions, bans, or any other actions taken by Discord. Use at your own risk.

This tool is **not affiliated with, endorsed by, or connected to Discord** in any way.
