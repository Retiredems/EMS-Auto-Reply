<div align="center">

<img src="assets/ems-autoreply-icon.svg" width="120" alt="EMS Auto-Reply" />

# EMS Auto-Reply

**Set-and-forget email auto-responder for your custom-domain mailbox.**

Rule-based, templated replies with attachments — sends once per sender,
never loops, runs quietly in your system tray.

![platform](https://img.shields.io/badge/platform-Windows%20%7C%20macOS-1A2540)
![status](https://img.shields.io/badge/build-stable-7CB518)
![license](https://img.shields.io/badge/license-Commercial-0E1830)

— Windows & macOS.

</div>

---

## What Is EMS Auto-Reply?

EMS Auto-Reply watches your inbox and answers incoming mail automatically,
using rules you define and HTML templates you design. It's built for
freelancers, small businesses, and anyone running a custom-domain mailbox
(Gmail/Google Workspace, Outlook, or any standard IMAP/SMTP host) who wants
professional, instant first responses without leaving a tab open.

You set the rules — by sender, domain, recipient alias, subject, or body
keywords — and pick which template each rule sends. The app polls your inbox
on a schedule, replies once per sender, and stays out of your way in the
system tray.

## Screenshots
<img width="1101" height="811" alt="Screenshot 2026-07-01 at 15 06 44" src="https://github.com/user-attachments/assets/dfdd122e-19ee-4406-8040-38b872d7adfa" />


## How Replies Work

| Layer | What it does |
|-------|--------------|
| **Rule matching** | First matching rule wins — match on sender, domain, alias (To), subject keywords, or body keywords |
| **Templates** | HTML templates with `{sender_name}`, `{sender_email}`, `{original_subject}`, `{date}` placeholders + plain-text auto-generated |
| **Attachments** | Attach one or more files per rule |
| **Per-sender dedup** | Each sender gets exactly one reply — no repeats, ever |
| **Anti-loop safety** | Skips mailer-daemons, auto-submitted mail, mailing lists, out-of-office, and your own address |
| **Sent-copy cleanup** | Optional: removes the reply from your Sent folder after sending (Gmail) — no clutter |
| **Dry-run mode** | Preview exactly who would be replied to, without sending a thing |

## Where Your Data Lives

Everything stays on your machine. Nothing is uploaded except license checks.

| Location | Contents |
|----------|----------|
| `app.db` | Rules, settings, reply history (per-sender dedup) |
| `templates/` | Your HTML reply templates |
| `attachments/` | Files attached by rules |
| `logs/` | Bounded diagnostic log (auto-capped — never grows unchecked) |

Your mailbox password is stored in the OS keychain (Windows Credential
Manager / macOS Keychain), never in plain text.

## Key Features

**Reliable reply engine**
- Polls every 10s / 30s / 1m / 5m (your choice)
- Rate-limited sends with configurable pause between messages
- One reply per sender, guaranteed

**Fully configurable**
- Visual rule editor with live match summary
- HTML template editor with placeholder variables
- Per-rule subject lines and attachments

**Polished, friendly UI**
- Light & dark themes
- System-tray operation with pause/resume
- Activity log of every send, skip, and error
- **Automatic update checks** — get notified and install new versions in-app

## Installation

### Windows
1. Download `EMS-Auto-Reply-Setup.exe` from [Releases](https://github.com/Retiredems/EMS-Auto-Reply/releases).
2. Run it. (Installs per-user — no admin prompt; updates install just as cleanly.)
3. Launch **EMS Auto-Reply** from the Start menu.

### macOS
1. Download `EMS_AutoReply_macOS.zip` from [Releases](https://github.com/Retiredems/EMS-Auto-Reply/releases).
2. Unzip and drag **EMS Auto-Reply.app** into Applications.
3. First launch: right-click → **Open** (unsigned build).

## Getting a License

EMS Auto-Reply runs on a free trial, then needs a license key.

| Plan | Price | Devices |
|------|-------|---------|
| Lifetime | **$100** | Up to **3 PCs** |

Get yours from the Telegram bot: **[@emsmailerbot](https://t.me/emsmailerbot)**

## How to Get a License Key

1. Open EMS Auto-Reply — the activation screen shows your **Hardware ID**.
2. Copy the Hardware ID.
3. Message **[@emsmailerbot](https://t.me/emsmailerbot)** and send your Hardware ID.
4. Pay and receive your license key.
5. Paste the key into the activation screen → **Activate**. Done.

## Input Format

**A rule** matches incoming mail and picks a template:

```
Name:     VIP clients
Match:    from_domain = @bigclient.com
Subject:  Re: {original_subject}
Template: vip.html
Attach:   rate-card.pdf
```

**A template** is HTML with placeholders:

```html
<p>Hi {sender_name},</p>
<p>Thanks for reaching out about "{original_subject}".
   We received your message on {date} and will reply within one business day.</p>
<p>— The Team</p>
```

## Settings

| Setting | Description |
|---------|-------------|
| Poll interval | How often the inbox is checked (10s–5m) |
| Max replies per poll | Cap sends per cycle to stay under provider limits |
| Pause between sends | Delay between messages |
| Reply once per sender | Per-sender dedup (recommended on) |
| Dry-run mode | Log who *would* be replied to, without sending |
| Delete reply from Sent | Remove the reply's Gmail Sent copy after sending |
| Minimize to tray | Keep running when the window is closed |
| Show notifications | Desktop notification on each reply |
| Start at login | Launch automatically when you sign in |
| Auto-check for updates | Notify + install new versions on launch |

## System Requirements

| | |
|---|---|
| **OS** | Windows 10/11 (64-bit) · macOS 11+ |
| **RAM** | 256 MB |
| **Disk** | ~120 MB installed |
| **Network** | Internet access for IMAP/SMTP + license check |

## Changelog

### 1.0.0
- First public release: rule-based templated auto-replies, per-sender dedup,
  anti-loop safety, attachments, dry-run, tray operation, light/dark themes,
  and in-app update checking.

## Other EMS Tools

| Tool | What it does |
|------|--------------|
| EMS Mailer | Bulk email sender |
| EMS Email Sorter | Sort & categorize mailing lists |
| EMS Email Verifier | Validate email deliverability |
| EMS Office365 Verifier | Check Office 365 mailboxes |
| EMS Honeypot Remover | Strip spam-trap addresses from lists |

## Support

- Issues: [GitHub Issues](https://github.com/Retiredems/EMS-Auto-Reply/issues)
- Telegram: **[@retiredems](https://t.me/retiredems)**

---

<div align="center">
Built with precision by Retiredems · Powered by PyQt6
</div>
