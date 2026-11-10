# Origin

Full-tree fork of `golang.org/x/crypto` with dependency bumps for intake scanning.

- Upstream commit: `2f1f834330b2d36ab3db8bfb33aaa1ac16794588`
- Pseudo-version reference: `v0.58.1-0.20261009181718-2f1f834330b2`
- Changes vs upstream:
  - `golang.org/x/net`: v0.60.0 → **v0.62.0** (clears CVE-2026-78661, CVE-2026-97045)
  - `golang.org/x/sys`: already v0.49.0 (≥ v0.44.0)
  - Module path rewritten to placeholder `github.com/ms-iipt/golang.org-x-crypto-CVEresolved`
  - Removed nested `_asm/**/go.mod` (code-gen only; pinned ancient deps that poison `trivy fs`)
  - Removed carved-out `openpgp/` nested module (GO-2026-5932 / unmaintained)
  - Removed `x509roots/fallback/go.mod` nested module file (code kept)
- License: BSD-style (LICENSE / PATENTS)

Prefer the bcrypt-only tree under `internal/bcrypt-intake/` if intake only needs password hashing.
