# Contributing to Octo-pus Registry

Thank you for your interest in contributing to **octo-pus**, the package registry for the Octo CLI package manager!

This guide will help you add, update, or maintain package definitions in the registry.

---

## How to Contribute

### 1. Adding a New Package

- Create a new folder under `packages/` with the package name (e.g., `packages/lazygit/`).
- Inside that folder, add one or more version YAML files describing the package following the schema.
- Each YAML file should include:
  - `name`, `version`, `description`, `homepage`, `license`
  - `dependencies` (if any)
  - `platforms` list with OS/arch-specific binaries, URLs, checksums, and hooks
- Use consistent formatting and indentation to keep files readable.

### 2. Updating an Existing Package

- Add new version YAML files under the package folder (e.g., `packages/lazygit/0.5.2.yaml`).
- Update existing package metadata if necessary (e.g., description, homepage).
- Do **not** remove or modify old versions unless fixing errors. Version history should be preserved.

### 3. Package Schema

- Follow the established YAML schema to ensure validation passes.
- Validate your files using `yamllint` and schema validation tools integrated into CI.

### 4. Pre- and Post-Install Hooks

- Use platform-specific scripts under `hooks.pre_install` and `hooks.post_install` as needed.
- Scripts should be compatible with the target OS shell (e.g., Bash for Linux/macOS, Batch for Windows).

### 5. Checksums & Security

- Always provide a valid SHA256 checksum for each binary URL to ensure integrity.
- Verify checksum matches the file you upload.

### 6. Submitting Your Changes

- Fork the repository and create a feature branch.
- Make your changes and test them locally if possible.
- Commit with clear, descriptive messages.
- Open a pull request describing your changes and why they’re needed.
- The CI pipeline will run linting and schema validation automatically.

---

## Additional Tips

- Keep package YAML files clean and minimal while complete.
- Avoid duplicate packages or versions.
- If you’re unsure about schema or formatting, open an issue for guidance.
- Respect semantic versioning when adding new package versions.

---

## Thank You!

Your contributions keep Octo-pus rich and reliable for the entire Octo community. We appreciate your help!

---
