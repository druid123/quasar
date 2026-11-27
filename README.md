# QUASAR

Cross-platform SSH client, dual-pane file manager, and remote desktop.

QUASAR is a native desktop app for SSH, files, and remote desktops. One SSH login opens the shell and SFTP together. Copies resume. Two panels move files between your disk, another server, or cloud storage. RDP brings clipboard, drives, sound, and smart cards with the session. An optional AI assistant waits for you before it runs a risky command.

Windows ships as a portable ZIP. Linux ships as a Fedora RPM. The interface is in English, Russian, German, Spanish, French, and Chinese.

## SSH terminal

- One authenticated session carries both the terminal and the SFTP browser.
- Sign in with a password, a private key, an agent, keyboard-interactive prompts, or an OpenSSH certificate kept in password storage.
- Jump hosts, HTTP CONNECT, SOCKS4, SOCKS4a, and SOCKS5.
- X11 forwarding and GSSAPI through the system OpenSSH client when the session needs them.
- Host keys are checked and a changed fingerprint needs an explicit accept.
- Split the workspace side by side or one above the other.
- Search the scrollback, record output to a UTF-8 file, and replay a startup macro.
- UTF-8, Windows-1251, CP866, KOI8-R, and Windows-1252.
- The file panel can follow the directory reported by the remote shell.

## Files

Two panels, one set of actions: copy, move, rename, create, delete, permissions, and archives.

- Disks, SFTP, and SCP, including hosts that have no SFTP.
- FTP with explicit or implicit TLS.
- SMB and NFS, including Kerberos for NFS.
- Amazon S3.
- Server-to-server copy, not only server-to-disk.
- Interrupted SFTP transfers resume. A finished transfer keeps the original time.
- A move deletes the source only after the copy succeeds.
- New files are created without wiping an existing one.
- Drag and drop between panels and into the SSH terminal.

## Remote desktop

**RDP.** Network Level Authentication, an RD Gateway, and smart-card sign-in. Redirect the clipboard, drive letters, folders, sound, microphone, printer, and ports. RemoteApp, an alternate shell, several monitors, and a persistent graphics cache.

**VNC.** A desktop session with TLS and a shared clipboard.

**Also on a tab.** Telnet, serial ports, raw TCP, and named pipes. Local PowerShell, Cmd, Bash, Zsh, and WSL. Wake-on-LAN. Local, remote, and dynamic SSH tunnels. WinRM on Windows.

## Network tools

- Live ping with a round-trip chart.
- Traceroute as a list and on a map.
- Port scanner, open local ports, and a view of the local network.

## Password storage

Connection profiles do not contain passwords. Secrets sit in local password storage protected by a master password (Argon2id and XChaCha20-Poly1305). The storage starts locked on every launch. Unlocking it lasts only until you quit.

## AI assistant

Off until you turn it on for a specific SSH session. QUASAR asks before a proposed command that rates as risky. Secrets are stripped from the context before anything is sent. Closing the session cancels the work in flight.

## Around the session

Command palette, macros with hotkeys, a scheduler, a text editor, an image viewer, themes, and a log of connection errors across SSH, RDP, VNC, FTP, SFTP, SMB, NFS, and S3. Temporary local HTTP, FTP, TFTP, Telnet, SSH, NFS, and VNC servers, each with its own consent and time limit.

## Questions people ask

**What is QUASAR?**  
A cross-platform SSH client with a dual-pane file manager and built-in RDP and VNC.

**Does one SSH login cover files and the shell?**  
Yes. The terminal and SFTP share one authenticated session, and SFTP transfers can resume.

**Where are passwords stored?**  
In local password storage, not in the connection profile. A master password unlocks them for the current run.

**Will the AI type commands by itself?**  
Only after you allow the assistant for that session, and risky commands still wait for confirmation.

## Releases & Installation

This repository hosts official verified release packages of QUASAR only; proprietary application source code is not published here.

- **Windows x64 (`windows` branch):** download `QUASAR-<version>-win64.zip` from [GitHub Releases](https://github.com/druid123/quasar/releases), extract the full archive, and run `QUASAR.exe`. Keep bundled DLLs, `manifest.json`, licenses, and notices next to the executable. Optional external components such as Microsoft Edge WebView2 Runtime, OpenSSH Client, WSL, and Mosh are not bundled.
- **Fedora x86_64 GNOME/Wayland (`linux` branch):** download `codebase-terminal-<version>-<release>.fc<fedora>.x86_64.rpm` from [GitHub Releases](https://github.com/druid123/quasar/releases) and install with `sudo dnf install ./codebase-terminal-<version>-<release>.fc<fedora>.x86_64.rpm`.
- **Update verification:** QUASAR checks public GitHub Releases and verifies release archives by byte size and SHA-256 before applying updates.

## Changelog

See [`RELEASE-NOTES.md`](RELEASE-NOTES.md) for the cumulative release history.

## License & Third-Party Notices

Copyright © 2026 Andrey Filatov, Egor Filatov (`qzartec`). All rights reserved for proprietary components.

- **Proprietary license:** QUASAR is proprietary closed-source software licensed free of charge for personal, educational, internal corporate, and commercial use under [`LICENSE.txt`](LICENSE.txt).
- **Redistribution:** redistribution is permitted only as a complete, unmodified distribution package preserving `LICENSE.txt`, attribution notices, third-party licenses, and required third-party source materials.
- **Alpha software:** QUASAR is an alpha release provided "AS IS" and "AS AVAILABLE" without warranties; see [`LICENSE.txt`](LICENSE.txt) for full terms and limitations.
- **Third-party materials:** third-party licenses, notices, CycloneDX SBOM, and required corresponding third-party sources (such as MPL-covered components and artwork/font notices) are included inside each release package: `THIRD-PARTY-NOTICES.txt`, `sbom.cdx.json`, `licenses/`, and `sources/` in Windows ZIP archives, and `/usr/share/licenses/codebase-terminal/` and `/usr/share/doc/codebase-terminal/` in Fedora RPM packages.
