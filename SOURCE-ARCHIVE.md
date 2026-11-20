# Import the ChatGPT NixOS Workbench v0.3.0 source archive

The full v0.3.0 source tree was generated as a local ChatGPT artifact. The GitHub connector available to this session can create and update text files, but it does not expose a direct upload-from-local-file action. Therefore this repository currently contains its initial README commit; the full archive has **not** been pushed by this session.

## Archive details

- File: `chatgpt-nixos-workbench-v0.3.0.zip`
- SHA-256 of the ZIP: see the checksum file supplied alongside the archive in the ChatGPT conversation.
- Project directory inside the ZIP: `chatgpt-nixos-workbench/`

## Import into this repository

Download the ZIP from the ChatGPT conversation, then run:

```bash
git clone https://github.com/adr1um/chatgpt-nixos-workbench.git
cd chatgpt-nixos-workbench

# Replace /path/to with the actual downloaded ZIP location.
unzip -o /path/to/chatgpt-nixos-workbench-v0.3.0.zip -d /tmp/chatgpt-nixos-workbench-import
cp -a /tmp/chatgpt-nixos-workbench-import/chatgpt-nixos-workbench/. .

git add -A
git status --short
git commit -m "feat: add NixOS Workbench v0.3.0 wizard and project docs"
git push origin main
```

Review `git status --short` before committing. Do not commit personal profile exports containing machine-specific secrets.

## Local validation

```bash
python3 tools/validate_catalog.py
node --check wizard/app.js
node tools/test_generator_runtime.cjs
```

A passing local JavaScript/JSON test is not a substitute for `nix flake check` on a machine with Nix installed.
