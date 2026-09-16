# URL / Repository Independence Audit

Target project repository: `https://github.com/faisin/adyetubar`

## Project-owned source/artifact downloads

The installer/project-owned artifacts are configured to use the target repository:

- `run.sh` -> `https://github.com/faisin/adyetubar.git`
- `manage_bundle.zip` -> `https://raw.githubusercontent.com/faisin/adyetubar/main/manage_bundle.zip`
- `bot_telegram.zip` -> `https://github.com/faisin/adyetubar/raw/main/bot_telegram.zip`
- Go module paths -> `github.com/faisin/adyetubar/...`

## External runtime dependencies

The project still references upstream services/software where the software is not owned by this repository, including Xray, acme.sh, Cloudflare WARP package repositories, wgcf, wireproxy, nginx package/signing infrastructure, IP information APIs, and Cloudflare API endpoints.

These URLs are **not project repository URLs** and should not be replaced with the GitHub repository URL: replacing an API endpoint or package repository with a GitHub raw URL would break the installer/functionality unless a compatible mirror/artifact is actually vendored into this repository.

## License handling

Project-specific license/activation enforcement that blocked installation/runtime has been removed. Third-party legal notices/licenses are intentionally not deleted merely because they contain the word "license"; those notices are not installer activation gates.
