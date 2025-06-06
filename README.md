# 🐙 octo-pus

**octo-pus** is the official package registry for [Octo CLI](https://github.com/your-org/octo), a fast, cross-platform package manager written in Go.

This repository contains structured metadata (`YAML`) for all packages supported by `octo`. It acts as the decentralized source of truth for how packages are fetched, extracted, and installed.

---

## 📦 What’s inside?

Each package is defined in its own YAML file inside the `packages/` directory. These [definitions](schema/package.schema.yml) include:

- Package name and version
- Platform-specific binaries (OS/Arch)
- Download URLs and file formats
- Install instructions (e.g., extracted binary path)


Example:

```yaml
name: bat
version: 0.24.0
description: A cat(1) clone with syntax highlighting and Git integration
platforms:
  - os: linux
    arch: amd64
    url: https://github.com/sharkdp/bat/releases/download/v0.24.0/bat-v0.24.0-x86_64-unknown-linux-gnu.tar.gz
    bin: bat
```


## 🚀 How Octo uses this


When you run a command like:

```bash
octo install bat
```

Octo fetches the `bat.yaml` definition from this repository, downloads the appropriate archive for your system, extracts it, and installs it to your system path.


## 🧑‍💻 Contributing

Want to add a new package or update an existing one?

-Fork this repo
- Add or edit a file in packages/
- Open a Pull Request

All package definitions are validated automatically via GitHub Actions. Please ensure your YAML file is valid and follows the schema.


## 📚 Related Projects

🔧 Octo CLI — the package manager
🐙 `octo install <package>` — powered by this repo
