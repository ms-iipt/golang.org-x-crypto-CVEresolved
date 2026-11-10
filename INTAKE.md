# Intake metadata checklist

Module: `github.com/ms-iipt/golang.org-x-crypto-CVEresolved`  
Tag: `v0.1.0` → commit `b6324cd` (immutable after sumdb publish; do not retarget)  
Release: https://github.com/ms-iipt/golang.org-x-crypto-CVEresolved/releases/tag/v0.1.0  

Note: This `INTAKE.md` and the expanded `README.md` live on `main` (ahead of the `v0.1.0` tag). The tagged module tree + Release archives match `proxy.golang.org` / `sum.golang.org`.

## Required (in-repo)

| File | Status |
|------|--------|
| `go.mod` | Present — module path + `go 1.26.0` |
| `go.sum` | Present — regenerated via `go mod tidy` as needed |
| `LICENSE` | Present (BSD-style) |
| `README.md` | Present on `main` — module path, tag, `go get`, bcrypt import, Go ≥ 1.26, origin note |

## Required (GitHub Release assets for “암호/검증 파일”)

| Asset | Status |
|-------|--------|
| `golang.org-x-crypto-CVEresolved-v0.1.0.tar.gz` | Published on Release `v0.1.0` |
| `golang.org-x-crypto-CVEresolved-v0.1.0.zip` | Published on Release `v0.1.0` |
| `SHA256SUMS` | Published — sha256 of the archives (usual integrity / “암호파일”) |

SHA256 (archives of tagged tree `b6324cd`):

```
f69efd88b5edca980bc48a10de689b76e4c18d27e704bc1edcdbfbf69f55947f  golang.org-x-crypto-CVEresolved-v0.1.0.tar.gz
5f10c8b6acf9bbe9e1015f28ab281a5b4088348588695f1c53e8ec0356a294e3  golang.org-x-crypto-CVEresolved-v0.1.0.zip
```

## Optional

| Item | Status |
|------|--------|
| `PATENTS` | Present (kept from upstream) |
| `ORIGIN.md` | Present — upstream commit + CVE-related dep bumps |
| `.gitignore` | Present (Go/build artifacts) |
| `SHA512SUMS` | Published alongside SHA256 |
| `SHA256SUMS.asc` (detached GPG signature) | **Skipped** — no GPG binary / secret key on the publishing machine. Do not invent a key. |
| proxy.golang.org listing | Indexed (use case-encoded path `.../golang.org-x-crypto-!c!v!eresolved/@v/v0.1.0.info`) |

## Proxy / discoverability probes

```bash
GOPROXY=https://proxy.golang.org,direct go list -m -json github.com/ms-iipt/golang.org-x-crypto-CVEresolved@v0.1.0
# Unescaped uppercase path → 400/404 from proxy URL; encode CVE → !c!v!e:
curl -sI https://proxy.golang.org/github.com/ms-iipt/golang.org-x-crypto-!c!v!eresolved/@v/v0.1.0.info
```

`go list` succeeds via proxy+direct. Raw unescaped `curl` to the module path with uppercase letters fails; the case-encoded URL returns 200.
