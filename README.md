# golang.org-x-crypto-CVEresolved

CVE-resolved intake mirror of [`golang.org/x/crypto`](https://pkg.go.dev/golang.org/x/crypto) for ms-iipt package-info / “암호파일” style checks.

## Module

| Item | Value |
|------|--------|
| Module path | `github.com/ms-iipt/golang.org-x-crypto-CVEresolved` |
| Release tag | `v0.1.0` |
| Go version | **≥ 1.26** (`go 1.26.0` in `go.mod`) |
| License | BSD-style (`LICENSE` / `PATENTS`) |

## Install

```bash
go get github.com/ms-iipt/golang.org-x-crypto-CVEresolved@v0.1.0
```

If `proxy.golang.org` returns 404 (common for newly published or org-visibility modules), use:

```bash
GOPROXY=direct go get github.com/ms-iipt/golang.org-x-crypto-CVEresolved@v0.1.0
```

Or consume the GitHub Release source archive / checksums listed in [`INTAKE.md`](./INTAKE.md).

## Import (bcrypt example)

```go
import "github.com/ms-iipt/golang.org-x-crypto-CVEresolved/bcrypt"
```

Other packages under this module follow the same prefix (for example `.../ssh`, `.../hkdf`).

## Origin

Full-tree fork of upstream `golang.org/x/crypto` at commit `2f1f834330b2d36ab3db8bfb33aaa1ac16794588`, with dependency bumps for intake scanning (`golang.org/x/net@v0.62.0`). See [`ORIGIN.md`](./ORIGIN.md).

## Intake metadata

See [`INTAKE.md`](./INTAKE.md) for the required vs optional intake file checklist and what was published on the `v0.1.0` GitHub Release (archives + `SHA256SUMS`).
