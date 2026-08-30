# lonefisher's Scoop Bucket

[![Tests](https://github.com/lonefisher/scoop-bucket/actions/workflows/ci.yml/badge.svg)](https://github.com/lonefisher/scoop-bucket/actions/workflows/ci.yml)
[![Excavator](https://github.com/lonefisher/scoop-bucket/actions/workflows/excavator.yml/badge.svg)](https://github.com/lonefisher/scoop-bucket/actions/workflows/excavator.yml)

Personal [Scoop](https://scoop.sh) bucket for Windows applications that are not available in the buckets I use.

## Add this bucket

```powershell
scoop bucket add lonefisher https://github.com/lonefisher/scoop-bucket
```

## Available manifests

### RHI

[RHI](https://github.com/RankFTW/RHI) is a ReShade HDR installer and graphics mod manager for Windows games.

```powershell
scoop install lonefisher/rhi
```

RHI requires the .NET 8 Desktop Runtime. If it is not already installed:

```powershell
scoop bucket add versions
scoop install versions/windowsdesktop-runtime-8.0
```

The RHI manifest is configured for Scoop's Inno Setup extraction and is automatically checked for upstream GitHub releases by the repository's Excavator workflow.

## Updating

Normal Scoop updates are sufficient:

```powershell
scoop update
scoop update rhi
```
