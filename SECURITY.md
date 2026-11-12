# Security

## Secrets

- Do not commit `.env` files, keys, tokens or passwords.
- Do not commit Steam files (`.vdf`, `.acf`). They hold account data.
- If a secret leaks, tell the maintainer. Rotate the secret.

## Logs

- Logs can hold account names, SteamIDs, file paths and machine names. Keep logs in logs/ (gitignored).
- Before you share a log, remove account names and SteamIDs. Replace the home path with `~`.

## Binaries

Do not commit game files, Apple D3DMetal files, Wine files or files of other projects.

## Threats

| Threat | Control |
|---|---|
| Account data in a public log | Redact before sharing. Gitignore logs |
| Malicious DLL in a PR | The maintainer rejects any binary in a PR |
| Account ban from game integrity checks | Never edit the game EXE. Test on a spare account when possible |
| Unlicensed code from another project | Copy none (decisions.md, D-001) |
