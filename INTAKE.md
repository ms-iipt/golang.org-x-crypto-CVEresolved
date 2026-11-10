# Intake metadata checklist

Module: `github.com/ms-iipt/golang.org-x-crypto-CVEresolved`  
Tag: `v0.1.0`  
Release: https://github.com/ms-iipt/golang.org-x-crypto-CVEresolved/releases/tag/v0.1.0

## Required (in-repo)

| File | Status |
|------|--------|
| `go.mod` | Present — module path + `go 1.26.0` |
| `go.sum` | Present — regenerated via `go mod tidy` as needed |
| `LICENSE` | Present (BSD-style) |
| `README.md` | Present — module path, tag, `go get`, bcrypt import, Go ≥ 1.26, origin note |

## Required (GitHub Release assets for “암호/검증 파일”)

| Asset | Status |
|-------|--------|
| `golang.org-x-crypto-CVEresolved-v0.1.0.tar.gz` | Published on Release `v0.1.0` |
| `golang.org-x-crypto-CVEresolved-v0.1.0.zip` | Published on Release `v0.1.0` |
| `SHA256SUMS` (or `SHA256SUMS.txt`) | Published — sha256 of the archives (usual integrity / “암호파일”) |

## Optional

| Item | Status |
|------|--------|
| `PATENTS` | Present (kept from upstream) |
| `ORIGIN.md` | Present — upstream commit + CVE-related dep bumps |
| `.gitignore` | Present (Go/build artifacts) |
| `SHA512SUMS` | Published when created alongside SHA256 |
| `SHA256SUMS.asc` (detached GPG signature) | **Skipped** — no GPG secret key on the publishing machine (`gpg` unavailable / no secret keys). Do not invent a key. |
| proxy.golang.org listing | May 404 until the public module proxy indexes the tag; use `GOPROXY=direct` or the Release zip |

## Proxy / discoverability probes

```bash
GOPROXY=https://proxy.golang.org,direct go list -m -json github.com/ms-iipt/golang.org-x-crypto-CVEresolved@v0.1.0
curl -sI https://proxy.golang.org/github.com/ms-iipt/golang.org-x-crypto-CVEresolved/@v/v0.1.0.info
```

If the proxy returns 404, intake scanners that fetch via the public proxy may need `GOPROXY=direct` or an uploaded Release zip + `SHA256SUMS`.
