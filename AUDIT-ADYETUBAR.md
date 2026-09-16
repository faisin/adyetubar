# Adyetubar repository audit

Target repository: `faisin/adyetubar`

## Changes applied

- Removed the project-specific install/runtime license guard and its systemd enforcer.
- Removed license preflight from `run.sh`, `setup.sh`, `manage.sh`, and Telegram installer/gateway.
- Removed the dedicated license-guard menu and stale license status display.
- Removed license-guard service/template/config/binary source files.
- Rebuilt `bot_telegram.zip` and `manage_bundle.zip` so nested artifacts match the cleaned source.
- Replaced old `superdecrypt-dev/autoscript` repository references with `faisin/adyetubar` where they are project/source references.
- Updated Go module paths/imports for the new repository.
- Removed the hard-coded Cloudflare API token; Cloudflare credentials must now be supplied through `CLOUDFLARE_API_TOKEN`.

## Verification

- Bash syntax: PASS.
- Python compilation: PASS.
- `tests/test_basic.py`: PASS.
- `tools/test-manage-router.sh`: PASS.
- `tools/test-manage-menu-labels.sh`: PASS.
- `tools/test-noninteractive.sh`: PASS.
- Go tests for `opt/edge/go`: PASS.
- Go tests for `opt/adblock/go`: PASS.
- Full repository scan: no `autoscript-license`, `AUTOSCRIPT_LICENSE`, old repository URL, or license-guard references remain outside the retained source `LICENSE` document and unrelated WARP+/external-tool license semantics.

## Important note

The repository's legal `LICENSE` file is retained. It is not an installation gate. Third-party dependency notices/licenses are also not removed merely to make the installer appear license-free. Before publishing, the repository owner should confirm that the chosen source license and all third-party obligations are appropriate for the code being redistributed.

## Operator requirements

Set Cloudflare credentials explicitly when DNS operations need them, for example:

`export CLOUDFLARE_API_TOKEN='...'`

Do not commit secrets into the repository.
