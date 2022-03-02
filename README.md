# oci-action
GitHub Actions for logging into an Open Container Initiative (OCI) registry and pushing an artifact.

[![license](https://img.shields.io/github/license/lucasmelin/oci-action.svg)](https://github.com/lucasmelin/oci-action/blob/main/LICENSE)
[![release](https://img.shields.io/github/release/lucasmelin/oci-action.svg)](https://github.com/lucasmelin/oci-action/releases/latest)
[![GitHub release date](https://img.shields.io/github/release-date/lucasmelin/oci-action.svg)](https://github.com/lucasmelin/oci-action/releases)

## Usage

```yaml
name: Push artifact
  on: pull_request

jobs:
  push:
    runs-on: ubuntu-latest
    steps:
      - uses: lucasmelin/oci-action@v1
        with:
          registry: myregistry.azurecr.io
          username: ${{ secrets.username }}
          password: ${{ secrets.password }}
          tags: samples/artifact:1.0
          artifact: ./file.txt
```