# Scoop Bucket for AI Tools

[![Tests](https://github.com/datagone/scoop-the-ai/actions/workflows/ci.yml/badge.svg)](https://github.com/datagone/scoop-the-ai/actions/workflows/ci.yml) [![Excavator](https://github.com/datagone/scoop-the-ai/actions/workflows/excavator.yml/badge.svg)](https://github.com/datagone/scoop-the-ai/actions/workflows/excavator.yml)

AI Tools' Manifests for [Scoop](https://scoop.sh), the Windows command-line installer.

## How do I install these manifests?

After manifests have been committed and pushed, run the following:

```pwsh
scoop bucket add ai https://github.com/datagone/scoop-the-ai
scoop install ai/$manifestname
```

## How do I contribute new manifests?

To make a new manifest contribution, please read the [Contributing
Guide](.github/CONTRIBUTING.md) and [App Manifests](https://github.com/ScoopInstaller/Scoop/wiki/App-Manifests) wiki page.
